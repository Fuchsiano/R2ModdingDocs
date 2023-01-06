Titanfall 2 Loadout system
===========================================



PilotLoadoutDef is a struct located in the sh_consts.gnut file.

PilotLoadoutDef contains the 

``name, suit, race, execution, ordnance, passive1, passive2, skinIndex, camoIndex`` of the pilot.

``primary, primaryAttachment, primaryMod1, primaryMod2, primaryMod3, primaryAttachments, primarySkinIndex, primaryCamoIndex`` of the primary weapon

``secondary, secondaryMod1, secondaryMod2, secondaryMod3, secondarySkinIndex, secondaryCamoIndex`` of the secondary weapon regardless of the type (anty titan or a pistol) 

``weapon3, weapon3Mod1, weapon3Mod2, weapon3Mod3, weapon3SkinIndex, weapon3CamoIndex`` of the third weapon slot 


GetCachedPilotLoadout




TitanLoadoutDef
.
 		SetPersistentTitanLoadout()
		IsValidTitanLoadoutProperty()
		GetChildLoadoutProperties()
		GetParentLoadoutProperty()
		PrintTitanLoadout()