Titanfall 2 LoadoutDef
===========================================

``PilotLoadoutDef`` and ``TitanLoadoutDef`` are structs located in the sh_consts.gnut file.


What are PilotLoadoutDef / TitanLoadoutDef Used for ? 
======================================================================================

* They are used to define a loadout a titan or pilot can spawn with.
* They are used to persist the loadout.
* They are **NOT** used to change a weapon on the fly 

PilotLoadoutDef contains the 
``name, suit, race, melee, execution, ordnance, passive1, passive2, skinIndex, camoIndex`` of the pilot.

``primary, primaryAttachment, primaryMod1, primaryMod2, primaryMod3, primaryAttachments, primarySkinIndex, primaryCamoIndex, primaryMods`` of the primary weapon

``secondary, secondaryMod1, secondaryMod2, secondaryMod3, secondarySkinIndex, secondaryCamoIndex, secondaryMods`` of the secondary weapon regardless of the type (anti titan or pistol) 

``weapon3, weapon3Mod1, weapon3Mod2, weapon3Mod3, weapon3SkinIndex, weapon3CamoIndex, weapon3Mods`` of the third weapon slot regardless of the type (anti titan or pistol) 

and ``ordnanceAmmo`` wich is used in the sp for ordnance ammo count   


TitanLoadoutDef meanwhile contain the  

``name, titanClass, primeTitanRef, primaryMod, special,antirodeo  passive1, passive2, passive3, passive4, passive5, passive6`` thank you Monarch I want to KMS
``voice, skinIndex, camoIndex, decalIndex, primarySkinIndex, primaryCamoIndex, difficulty, isPrime, primeSkinIndex, primeCamoIndex, primeDecalIndex, showArmBadge`` of the titan as well as 
``melee, coreAbility, primary, primaryAttachment, primaryMods, ordnance, ordnanceMods, specialMods, antirodeoMods, titanExecution``




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
	void function AddCallback_OnUpdateDerivedPilotLoadout( void functionref( PilotLoadoutDef newPilotLoadout ) callbackFunc )

	void function AddCallback_OnUpdateDerivedTitanLoadout( void functionref( TitanLoadoutDef newTitanLoadout ) callbackFunc )


    // also gives the corresponding player as a parameter 
	void function AddCallback_OnUpdateDerivedPlayerTitanLoadout( void functionref( entity player, TitanLoadoutDef newTitanLoadout ) callbackFunc )

What does what 
===========================================

PilotLoadoutDef
^^^^^^^^^^^^^^^^^

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
	 - the primary weapon not limited to time 
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
	 - the third mod of the weapon **READ ONLY** e.g. fast reload

string 			
secondary
string 			secondaryMod1
string 			secondaryMod2
string 			secondaryMod3
string 			weapon3
string 			weapon3Mod1
string 			weapon3Mod2
string 			weapon3Mod3
string 			ordnance
string 			passive1
string 			passive2
int				skinIndex
int				camoIndex
int 			primarySkinIndex
int 			primaryCamoIndex
int 			secondarySkinIndex
int 			secondaryCamoIndex
int 			weapon3SkinIndex
int 			weapon3CamoIndex


Usefull stuff
===========================================

.. code-block:: javascript

	//Prints the titanloadout form player at index to the console 
	void function PrintTitanLoadoutIndex( entity player, int index )

	//Prints the pilotloadout form player at index to the console 
	void function PrintPilotLoadoutIndex( entity player, int index )



TitanLoadoutDef

SetPersistentTitanLoadout()
IsValidTitanLoadoutProperty()
GetChildLoadoutProperties()
GetParentLoadoutProperty()
PrintTitanLoadout()



.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - test1 row 1, column 1
     - Heading row 1, column 2
     - Heading row 1, column 3
   * - Row 1, column 1
     - Nutttttte
     - Row 1, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3