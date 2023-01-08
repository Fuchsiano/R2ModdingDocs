Titanfall 2 LoadoutDef
===========================================

``PilotLoadoutDef`` and ``TitanLoadoutDef`` are structs located in the sh_consts.gnut file.


What are PilotLoadoutDef / TitanLoadoutDef Used for ? 
======================================================================================

* They are used to define a loadout a titan or pilot can spawn with.
* They are used to persist the loadout.
* They are **NOT** used to change a weapon on the fly 


.. list-table:: PilotLoadoutDef
   :widths: 25 25 50
   :header-rows: 1

   * - variable
     - type
     - description
   * - name
     - string
     - the UI name for this loadout
   * - suit
     - string
     - the model the Pilot should use
   * - race
     - string
     - wether the Pilot is male or female
   * - execution
     - string
     - the execution
   * - primary
     - string
     - the primary weapon. limited to Primary weapons NOTE: when changing this the mods and visors wont be changed so mods / visors exclusive to the gun will cause a server crash 
   * - primaryAttachment
     - string
     - the scope of the primary weapon
   * - primaryMod1
     - string
     - the first mod of the weapon **READ ONLY** e.g. fast reload 
   * - primaryMod2
     - string
     - the second mod of the weapon **READ ONLY** e.g. fast reload 
   * - primaryMod3
     - string
     - the third mod of the weapon **READ ONLY** e.g. fast reload. Normaly Titanfall uses this for the Pro-Screen but this is a normal mod slot it can hold any mod
   * - primaryMods
     - array<string>
     - the mods the gun will use **change this to edit weapon mods**        
   * - primaryAttachments
     - string
     - the Attachments a primary gun has e.g. scopes. Titanfall edits this array so you need to use the clone keyword 
   * - secondary
     - string
     - the secondary weapon, ether a pistol or anti titan weapon but can also hold a primary weapon 
   * - secondaryMod1
     - string
     - the first mod of the weapon **READ ONLY** e.g. fast reload 
   * - secondaryMod2
     - string
     - the second mod of the weapon **READ ONLY** e.g. fast reload 
   * - secondaryMod3
     - string
     - the third mod of the weapon **READ ONLY** e.g. fast reload 
   * - secondaryMods
     - array<string>
     - the mods the gun will use **change this to edit weapon mods**
   * - weapon3
     - string
     - the third weapon, ether a pistol or anti titan weapon but can also hold a primary weapon 
   * - weapon3Mod1
     - string
     - the first mod of the weapon **READ ONLY** e.g. fast reload 
   * - weapon3Mod2
     - string
     - the second mod of the weapon **READ ONLY** e.g. fast reload 
   * - weapon3Mod3
     - string
     - the third mod of the weapon **READ ONLY** e.g. fast reload 
   * - weapon3Mods
     - array<string>
     - the mods the gun will use **change this to edit weapon mods**
   * - ordnance
     - string
     - the grenade the pilot uses e.g. frag grenade 
   * - passive1
     - string
     - the first kit the pilot uses e.g. fast regen 
   * - passive2
     - string
     - the second kit the pilot uses e.g. kill report
   * - skinIndex
     - int
     - the skin the pilot uses 
   * - camoIndex
     - int
     - the colors the pilot uses
   * - primarySkinIndex
     - int
     - the skin the gun uses e.g. Masterworks kraber or the default skin
   * - primaryCamoIndex
     - int
     - the colors the gun uses
   * - secondarySkinIndex
     - int
     - the skin the gun uses e.g. Masterworks kraber or the default skin
   * - secondaryCamoIndex
     - int
     - the colors the gun uses
   * - weapon3SkinIndex
     - int
     - the skin the gun uses e.g. Masterworks kraber or the default skin
   * - weapon3CamoIndex
     - int
     - the colors the gun uses





.. list-table:: TitanLoadoutDef
   :widths: 25 25 50
   :header-rows: 1

   * - variable
     - type
     - description
   * - name
     - string
     - the name of the loadout
   * - titanClass
     - string
     - the name of the used titan e.g. ion / northstar ... Note: changing this value results in many errors. Its better to load a different titan loadout from persistent vars 
   * - primaryMod
     - string
     - mods for the primary weapon. Titanfall auto set this property based on the selectet titan, changing this can cause crashes  
   * - special
     - string
     - the defensive ability. e.g vortex shield 
   * - antirodeo
     - string
     - the middle ability of a titan e.g  Hover 
   * - passive1
     - string
     - the first passive a titan has. Titanfall uses this for the shared passives e.g.  overcore
   * - passive2
     - string
     - the second passive a titan has. Titanfall uses this for the unique passives e.g.  Tempered Plating
   * - passive3
     - string
     - the third passive a titan has. Titanfall uses this for dome shield/ warpfall 
   * - passive4
     - string
     - the fourth passive a titan has. Titanfall uses this only for Monarchs first upgrade core
   * - passive5
     - string
     - the fith passive a titan has. Titanfall uses this only for Monarchs second upgrade core
   * - passive6
     - string
     - the sixth passive a titan has. Titanfall uses this only for Monarchs third upgrade core
   * - voice
     - string
     - the voice your titan has
   * - skinIndex
     - int
     - the skin the titan uses. 
   * - camoIndex
     - int
     - the camo the titan uses. 
   * - decalIndex
     - int
     - the decal the titan uses. 
   * - primarySkinIndex
     - int
     - the skin the gun uses. 
   * - primaryCamoIndex
     - int
     - the camo the gun uses. 
   * - difficulty
     - int
     - the difficulty used in frontier def 
   * - showArmBadge
     - int
     - wether or not the arm badge should be displayed 
   * - melee
     - string
     - what type of melee your titan uses 
   * - coreAbility
     - string
     - what core your titan uses  
   * - primary
     - string
     - what weapon your titan uses 
   * - primaryAttachment
     - string
     - the Attachments used by the primary weapon
   * - primaryMods
     - array<string>
     - the mods your weapon the primary weapon
   * - ordnance
     - string
     - the faar right abuility of the titan e.g. laser shot
   * - ordnanceMods
     - array<string>
     - the mods your ordnance have 
   * - specialMods
     - array<string>
     - the mods your special have 
   * - antirodeoMods
     - array<string>
     - the mods your antirodeo have 
   * - isPrime
     - string
     - a string wether the titan should spawn as prime  	titan_is_not_prime or titan_is_prime     ask respawn about this choice 
   * - titanExecution
     - string
     - the execution your titan will do  
   * - primeSkinIndex
     - int
     - the prime and none prime titans have different index  
   * - primeDecalIndex
     - int
     - the prime and none prime titans have different index  
   * - primeCamoIndex
     - int
     - the prime and none prime titans have different index  


``name, titanClass, primeTitanRef, primaryMod, special,antirodeo  passive1, passive2, passive3, passive4, passive5, passive6`` thank you Monarch I want to KMS
``voice, skinIndex, camoIndex, decalIndex, primarySkinIndex, primaryCamoIndex, difficulty, isPrime, primeSkinIndex, primeCamoIndex, primeDecalIndex, showArmBadge`` of the titan as well as 
``melee, coreAbility, primary, primaryAttachment, primaryMods, ordnance, ordnanceMods, specialMods, antirodeoMods, titanExecution``


Limitations
===========================================

* loadouts cant exclude a weapon meaning a player will always spawn with a full kit. weapons/ordnance .... need to be taken away after the player spawns 
* you can only change the player loadout while the player is dead otherwise a text will apear saying the loadout will change after they respawn 
* when using LoadoutGracePeriodEnabled player can change their loadout after leaving the dropship negating your loadout changes 
* stacking mods on the same weapon will result in a server crash


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

The `Interstellar.BanMod <https://github.com/Neoministein/Interstellar.BanSystem/blob/master/Interstellar.BanSystem/mod/scripts/vscripts/_banLogic.gnut >` is just using loadouts to ban weapons and equipment.

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


