Titanfall 2 LoadoutDef
===========================================

``PilotLoadoutDef`` and ``TitanLoadoutDef`` are structs located in the sh_consts.gnut file.


What are PilotLoadoutDef / TitanLoadoutDef Used for ? 
======================================================================================

* They are used to define a loadout a titan or pilot can spawn with.
* They are used to persist the loadout.
* They are **NOT** used to change a weapon on the fly 

.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - type
     - variable
     - description
   * - string
     - name
     - the UI name for this loadout
   * - string
     - suit
     - the model the Pilot should use
   * - string
     - race
     - wether the Pilot is male or female
   * - string
     - execution
     - the execution
   * - string
     - primary
     - the primary weapon. limited to Primary weapons NOTE: when changing this the mods and visors wont be changed so mods / visors exclusive to the gun will cause a server crash 
   * - string
	 - primary
	 - the primary weapon 
   * - string
	 - primaryAttachment
	 - the scope of the primary weapon
   * - string
	 - primaryMod1
	 - the first mod of the weapon **READ ONLY** e.g. fast reload 
   * - string
	 - primaryMod2
	 - the second mod of the weapon **READ ONLY** e.g. fast reload 
   * - string
	 - primaryMod3
	 - the third mod of the weapon **READ ONLY** e.g. fast reload. Normaly Titanfall uses this for the Pro-Screen but this is a normal mod slot it can hold any mod
   * - array<string>
	 - primaryMods
	 - the mods the gun will use **change this to edit weapon mods**	 	 
.. list-table:: PilotLoadoutDef
   :widths: 25 25 50
   :header-rows: 1
   
   * - type
     - variable
     - description
   * - string
     - name
     - the UI name for this loadout
   * - string
     - suit
     - the model the Pilot should use   
   * - string
     - race
     - wether the Pilot is male or female
   * - string
     - execution
     - the execution
   * - string
     - primary
     - the primary weapon. limited to Primary weapons NOTE: when changing this the mods and visors wont be changed so mods / visors exclusive to the gun will cause a server crash 
   * - string
	 - primary
	 - the primary weapon 


.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - Heading row 1, column 1
     - Heading row 1, column 2
     - Heading row 1, column 3
   * - Row 1, column 1
     -
     - Row 1, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3  
TitanLoadoutDef meanwhile contain the  

``name, titanClass, primeTitanRef, primaryMod, special,antirodeo  passive1, passive2, passive3, passive4, passive5, passive6`` thank you Monarch I want to KMS
``voice, skinIndex, camoIndex, decalIndex, primarySkinIndex, primaryCamoIndex, difficulty, isPrime, primeSkinIndex, primeCamoIndex, primeDecalIndex, showArmBadge`` of the titan as well as 
``melee, coreAbility, primary, primaryAttachment, primaryMods, ordnance, ordnanceMods, specialMods, antirodeoMods, titanExecution``


Limitations
===========================================

* loadouts cant exclude a weapon meaning a player will always spawn with a full kit. weapons/ordnance .... need to be taken away after the player spawns 
* you can only change the player loadout while the player is dead otherwise a text will apear saying the loadout will change after they respawn 
* when using LoadoutGracePeriodEnabled player can change their loadout after leaving the dropship negating your loadout changes 



How to obtain the Loadouts ?
===========================================

First of all you should always use the variations sparingly to not trigger Callbacks unnecessary or even get stuck in an endless loop.	
Second you should always use the clone keyword when you want to edit the loadout, without creating a clone of the loadout in memory you would change the loadout permanently.     

variation 1 

.. code-block:: javascript
	
	// get the active Pilot / Titan loadouts 
	PilotLoadoutDef function GetActivePilotLoadout( entity player )

	TitanLoadoutDef function GetActiveTitanLoadout( entity player )


variation 2

.. code-block:: javascript

	// get the loadout at index from all loadouts the player has
	/*Note: 
		a player has 10 Pilot loadouts
		and 7 Titan loadouts
	*/
	PilotLoadoutDef function GetPilotLoadoutFromPersistentData( entity player, int loadoutIndex )
	
	TitanLoadoutDef function GetTitanLoadoutFromPersistentData( entity player, int loadoutIndex )


variation 3

.. code-block:: javascript

	//there are Callbacks for when the player updates his loadout  
	/* Note: 
		be carefull with applying loadouts in the callbacks. can lead to infinet loops   
	*/
	void function AddCallback_OnUpdateDerivedPilotLoadout( void functionref( PilotLoadoutDef newPilotLoadout ) callbackFunc )

	void function AddCallback_OnUpdateDerivedTitanLoadout( void functionref( TitanLoadoutDef newTitanLoadout ) callbackFunc )


    // also gives the corresponding player as a parameter 
	void function AddCallback_OnUpdateDerivedPlayerTitanLoadout( void functionref( entity player, TitanLoadoutDef newTitanLoadout ) callbackFunc )



Examples
===========================================

The `Interstellar.BanMod <https://github.com/Neoministein/Interstellar.BanSystem >` is just using loadouts to ban weapons and equipment.

Example "Pilot classes"
^^^^^^^^^^^^^^^^^^^^^^^^
a gamemode where a player can select a ``class`` in UI. We can get the selected class by calling the hypothetical function "getPilotClass"

the classes are 

* "gunner" a pilot wielding a L-star 
* "fastBoy"
* "sniper"  
	

Usefull stuff
===========================================

.. code-block:: javascript

	//Prints the titanloadout form player at index to the console 
	void function PrintTitanLoadoutIndex( entity player, int index )

	//Prints the pilotloadout form player at index to the console 
	void function PrintPilotLoadoutIndex( entity player, int index )


