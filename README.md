# Celeste_Pvp_BalancePatch




-- Tutorial For Luciano (by PF2K)


Okay so I'm not very good at writing coding tutorials (not good at all, actually) so I'm gonna show it with an example instead. Suppose we want to give a new functionality to Persian Mounted Archers' Champion upgrade. Currently the Champion tech for both PvE and PvP is the same. 800 gold: 1.5x bonus vs. Cav and -50% gold cost. Let's imagine that we want to change this tech so that in PvP mode it gives 1.5x bonus vs Cav and -20% Wood cost and -50% Gold cost and change the upgrade's cost to 600 gold (from 800). Here's how we do it:

1. We go to techtreex.xml

We add in this tech to the tech tree:

> <Tech name="PvP_PersiaTechMountedArcher_Upgrade1" type="Normal">
>    <DBID>5248</DBID>
>    <DisplayNameID>64619</DisplayNameID>
>    <Cost resourcetype="Gold">600.0000</Cost>
>    <ResearchPoints>60.0000</ResearchPoints>
>    <Status>UNOBTAINABLE</Status>
>    <Icon>\UserInterface\Icons\Techs\C04MountedArcherS_ua</Icon>
>    <RolloverTextID>64618</RolloverTextID>
>    <ContentPack>6</ContentPack>
>    <Flag>IsAward</Flag>
>    <Prereqs>
>      <SpecificAge>Age3</SpecificAge>
>    </Prereqs>
>    <Effects>
>      <Effect type="Data" amount="0.5000" scaling="0.0000" subtype="Cost" resource="Gold" relativity="Percent">
>       <Target type="ProtoUnit">Pe_Arc_MountedArcher</Target>
>      </Effect>
>	    <Effect type="Data" amount="0.8000" scaling="0.0000" subtype="Cost" resource="Wood" relativity="Percent">
>        <Target type="ProtoUnit">Pe_Arc_MountedArcher</Target>
>      </Effect>
>      <Effect type="Data" amount="1.5000" scaling="0.0000" subtype="DamageBonus" unittype="AbstractCavalry" allactions="1" relativity="Percent">
>        <Target type="ProtoUnit">Pe_Arc_MountedArcher</Target>
>      </Effect>
>      <Effect type="SetName" proto="Pe_Arc_MountedArcher" culture="none" newName="64620"></Effect>
>    </Effects>
>  </Tech>
  
  
  
  2. We go to techtreexStatlessOverrides.xml and then we add in this line:
  
>    <Tech name="PersiaTechMountedArcher_Upgrade1">PVP_PersiaTechMountedArcher_Upgrade1</Tech>
	
	
	I hope that does it! :D
	
	-PF2K
