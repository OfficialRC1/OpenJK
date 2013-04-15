PLATFORM=$(shell uname|tr A-Z a-z)

CC			= gcc
CXX			= g++
B			= build

ifeq ($(PLATFORM),darwin)
	DLL_EXT		= dylib
	BINARY_FMT	= macho
else
	DLL_EXT		= so
	BINARY_FMT	= elf
endif

GAME_NAME		= $(B)/jagamei386.$(DLL_EXT)
GAME_CFLAGS		= -m32 -I.  -fpermissive -D_M_IX86 -DNDEBUG -DMISSIONPACK -DJK2AWARDS -DFINAL_BUILD -D__NO_JK2
GAME_LDFLAGS		= -m32 -shared -lm
GAME_OBJS		= $(B)/game/AI_Animal.o \
			  $(B)/game/AI_AssassinDroid.o \
			  $(B)/game/AI_Atst.o \
			  $(B)/game/AI_BobaFett.o \
			  $(B)/game/AI_Civilian.o \
			  $(B)/game/AI_Default.o \
			  $(B)/game/AI_Droid.o \
			  $(B)/game/AI_GalakMech.o \
			  $(B)/game/AI_Glider.o \
			  $(B)/game/AI_Grenadier.o \
			  $(B)/game/AI_HazardTrooper.o \
			  $(B)/game/AI_Howler.o \
			  $(B)/game/AI_ImperialProbe.o \
			  $(B)/game/AI_Interrogator.o \
			  $(B)/game/AI_Jedi.o \
			  $(B)/game/AI_Mark1.o \
			  $(B)/game/AI_Mark2.o \
			  $(B)/game/AI_MineMonster.o \
			  $(B)/game/AI_Rancor.o \
			  $(B)/game/AI_Remote.o \
			  $(B)/game/AI_RocketTrooper.o \
			  $(B)/game/AI_SaberDroid.o \
			  $(B)/game/AI_SandCreature.o \
			  $(B)/game/AI_Seeker.o \
			  $(B)/game/AI_Sentry.o \
			  $(B)/game/AI_Sniper.o \
			  $(B)/game/AI_Stormtrooper.o \
			  $(B)/game/AI_Tusken.o \
			  $(B)/game/AI_Utils.o \
			  $(B)/game/AI_Wampa.o \
			  $(B)/game/g_active.o \
			  $(B)/game/g_breakable.o \
			  $(B)/game/g_camera.o \
			  $(B)/game/g_client.o \
			  $(B)/game/g_cmds.o \
			  $(B)/game/g_combat.o \
			  $(B)/game/g_emplaced.o \
			  $(B)/game/g_functions.o \
			  $(B)/game/g_fx.o \
			  $(B)/game/g_headers.o \
			  $(B)/game/g_inventory.o \
			  $(B)/game/g_itemLoad.o \
			  $(B)/game/g_items.o \
			  $(B)/game/g_main.o \
			  $(B)/game/g_mem.o \
			  $(B)/game/g_misc.o \
			  $(B)/game/g_misc_model.o \
			  $(B)/game/g_missile.o \
			  $(B)/game/g_mover.o \
			  $(B)/game/g_nav.o \
			  $(B)/game/g_navigator.o \
			  $(B)/game/g_navnew.o \
			  $(B)/game/g_object.o \
			  $(B)/game/g_objectives.o \
			  $(B)/game/g_rail.o \
			  $(B)/game/g_ref.o \
			  $(B)/game/g_roff.o \
			  $(B)/game/g_savegame.o \
			  $(B)/game/g_session.o \
			  $(B)/game/g_spawn.o \
			  $(B)/game/g_svcmds.o \
			  $(B)/game/g_target.o \
			  $(B)/game/G_Timer.o \
			  $(B)/game/g_trigger.o \
			  $(B)/game/g_turret.o \
			  $(B)/game/g_usable.o \
			  $(B)/game/g_utils.o \
			  $(B)/game/g_weapon.o \
			  $(B)/game/g_weaponLoad.o \
			  $(B)/game/NPC.o \
			  $(B)/game/NPC_behavior.o \
			  $(B)/game/NPC_combat.o \
			  $(B)/game/NPC_goal.o \
			  $(B)/game/NPC_misc.o \
			  $(B)/game/NPC_move.o \
			  $(B)/game/NPC_reactions.o \
			  $(B)/game/NPC_senses.o \
			  $(B)/game/NPC_sounds.o \
			  $(B)/game/NPC_spawn.o \
			  $(B)/game/NPC_stats.o \
			  $(B)/game/NPC_utils.o \
			  $(B)/game/q_math.o \
			  $(B)/game/genericparser2.o \
			  $(B)/game/q_shared.o \
			  $(B)/game/wp_saber.o \
			  $(B)/game/wp_saberLoad.o \
			  $(B)/icarus/BlockStream.o \
			  $(B)/icarus/IcarusImplementation.o \
			  $(B)/game/Q3_Interface.o \
			  $(B)/icarus/Sequence.o \
			  $(B)/icarus/Sequencer.o \
			  $(B)/icarus/TaskManager.o \
			  $(B)/game/bg_misc.o \
			  $(B)/game/bg_pangles.o \
			  $(B)/game/bg_panimate.o \
			  $(B)/game/bg_pmove.o \
			  $(B)/game/bg_slidemove.o \
			  $(B)/cgame/cg_camera.o \
			  $(B)/cgame/cg_consolecmds.o \
			  $(B)/cgame/cg_credits.o \
			  $(B)/cgame/cg_draw.o \
			  $(B)/cgame/cg_drawtools.o \
			  $(B)/cgame/cg_effects.o \
			  $(B)/cgame/cg_ents.o \
			  $(B)/cgame/cg_event.o \
			  $(B)/cgame/cg_headers.o \
			  $(B)/cgame/cg_info.o \
			  $(B)/cgame/cg_lights.o \
			  $(B)/cgame/cg_localents.o \
			  $(B)/cgame/cg_main.o \
			  $(B)/cgame/cg_marks.o \
			  $(B)/cgame/cg_players.o \
			  $(B)/cgame/cg_playerstate.o \
			  $(B)/cgame/cg_predict.o \
			  $(B)/cgame/cg_scoreboard.o \
			  $(B)/cgame/cg_servercmds.o \
			  $(B)/cgame/cg_snapshot.o \
			  $(B)/cgame/cg_text.o \
			  $(B)/cgame/cg_view.o \
			  $(B)/cgame/cg_weapons.o \
			  $(B)/cgame/FX_ATSTMain.o \
			  $(B)/cgame/FX_Blaster.o \
			  $(B)/cgame/FX_Bowcaster.o \
			  $(B)/cgame/FX_BryarPistol.o \
			  $(B)/cgame/FX_Concussion.o \
			  $(B)/cgame/FX_DEMP2.o \
			  $(B)/cgame/FX_Disruptor.o \
			  $(B)/cgame/FX_Emplaced.o \
			  $(B)/cgame/FX_Flechette.o \
			  $(B)/cgame/FX_HeavyRepeater.o \
			  $(B)/cgame/FX_NoghriShot.o \
			  $(B)/cgame/FX_RocketLauncher.o \
			  $(B)/cgame/FX_TuskenShot.o \
			  $(B)/cgame/FxPrimitives.o \
			  $(B)/cgame/FxScheduler.o \
			  $(B)/cgame/FxSystem.o \
			  $(B)/cgame/FxTemplate.o \
			  $(B)/cgame/FxUtil.o \
			  $(B)/Ratl/ratl.o \
			  $(B)/Ravl/CBounds.o \
			  $(B)/Ravl/CVec.o \
			  $(B)/Rufl/hfile.o \
			  $(B)/Rufl/hstring.o \
			  $(B)/game/AnimalNPC.o \
			  $(B)/game/bg_vehicleLoad.o \
			  $(B)/game/FighterNPC.o \
			  $(B)/game/g_vehicles.o \
			  $(B)/game/SpeederNPC.o \
			  $(B)/game/WalkerNPC.o \
			  $(B)/cgame/cg_syscalls.o \
			  $(B)/ui/gameinfo.o \
			  $(B)/qcommon/tri_coll_test.o
#$(B)/game/bg_lib.o \


ENGINE_NAME		= $(B)/jasp
ENGINE_CFLAGS		+= -m32 -fpermissive -w -DNDEBUG -DFINAL_BUILD -D_M_IX86 -I. -I/Library/Frameworks/SDL2.framework/Versions/A/Headers/
ENGINE_LDFLAGS		= -m32
ifeq ($(PLATFORM),darwin)
	ENGINE_LDFLAGS		+= -framework OpenGL -framework OpenAL -framework SDL2
else
	ENGINE_LDFLAGS		+= -lGL -lopenal
endif
ENGINE_OBJS		= $(B)/engine/client/cl_cgame.o \
			  $(B)/engine/client/cl_cin.o \
			  $(B)/engine/client/cl_console.o \
			  $(B)/engine/client/cl_input.o \
			  $(B)/engine/client/cl_keys.o \
			  $(B)/engine/client/cl_main.o \
			  $(B)/engine/client/cl_parse.o \
			  $(B)/engine/client/cl_scrn.o \
			  $(B)/engine/client/cl_ui.o \
			  $(B)/engine/client/cl_mp3.o \
			  $(B)/engine/qcommon/cm_draw.o \
			  $(B)/engine/qcommon/cm_load.o \
			  $(B)/engine/qcommon/cm_patch.o \
			  $(B)/engine/qcommon/cm_polylib.o \
			  $(B)/engine/qcommon/cm_randomterrain.o \
			  $(B)/engine/qcommon/cm_shader.o \
			  $(B)/engine/qcommon/cm_terrain.o \
			  $(B)/engine/qcommon/cm_terrainmap.o \
			  $(B)/engine/qcommon/cm_test.o \
			  $(B)/engine/qcommon/cm_trace.o \
			  $(B)/engine/qcommon/cmd.o \
			  $(B)/engine/qcommon/common.o \
			  $(B)/engine/qcommon/cvar.o \
			  $(B)/engine/qcommon/files_common.o \
			  $(B)/engine/qcommon/files_pc.o \
			  $(B)/engine/qcommon/hstring.o \
			  $(B)/engine/qcommon/md4.o \
			  $(B)/engine/qcommon/msg.o \
			  $(B)/engine/qcommon/net_chan.o \
			  $(B)/engine/game/q_math.o \
			  $(B)/engine/game/q_shared.o \
			  $(B)/engine/qcommon/stringed_ingame.o \
			  $(B)/engine/qcommon/stringed_interface.o \
			  $(B)/engine/qcommon/strip.o \
			  $(B)/engine/qcommon/unzip.o \
			  $(B)/engine/qcommon/z_memman_pc.o \
			  $(B)/engine/server/sv_ccmds.o \
			  $(B)/engine/server/sv_client.o \
			  $(B)/engine/server/sv_game.o \
			  $(B)/engine/server/sv_init.o \
			  $(B)/engine/server/sv_main.o \
			  $(B)/engine/server/sv_savegame.o \
			  $(B)/engine/server/sv_snapshot.o \
			  $(B)/engine/server/sv_world.o \
			  $(B)/engine/server/exe_headers.o \
			  $(B)/engine/client/snd_ambient.o \
			  $(B)/engine/client/snd_dma.o \
			  $(B)/engine/client/snd_mem.o \
			  $(B)/engine/client/snd_mix.o \
			  $(B)/engine/client/snd_music.o \
			  $(B)/engine/mp3code/cdct.o \
			  $(B)/engine/mp3code/csbt.o \
			  $(B)/engine/mp3code/csbtb.o \
			  $(B)/engine/mp3code/csbtl3.o \
			  $(B)/engine/mp3code/cup.o \
			  $(B)/engine/mp3code/cupini.o \
			  $(B)/engine/mp3code/cupl1.o \
			  $(B)/engine/mp3code/cupl3.o \
			  $(B)/engine/mp3code/cwin.o \
			  $(B)/engine/mp3code/cwinb.o \
			  $(B)/engine/mp3code/cwinm.o \
			  $(B)/engine/mp3code/hwin.o \
			  $(B)/engine/mp3code/l3dq.o \
			  $(B)/engine/mp3code/l3init.o \
			  $(B)/engine/mp3code/mdct.o \
			  $(B)/engine/mp3code/mhead.o \
			  $(B)/engine/mp3code/msis.o \
			  $(B)/engine/mp3code/towave.o \
			  $(B)/engine/mp3code/uph.o \
			  $(B)/engine/mp3code/upsf.o \
			  $(B)/engine/mp3code/wavep.o \
			  $(B)/engine/renderer/matcomp.o \
			  $(B)/engine/renderer/tr_WorldEffects.o \
			  $(B)/engine/renderer/tr_arioche.o \
			  $(B)/engine/renderer/tr_backend.o \
			  $(B)/engine/renderer/tr_bsp.o \
			  $(B)/engine/renderer/tr_cmds.o \
			  $(B)/engine/renderer/tr_draw.o \
			  $(B)/engine/renderer/tr_curve.o \
			  $(B)/engine/renderer/tr_font.o \
			  $(B)/engine/renderer/tr_ghoul2.o \
			  $(B)/engine/renderer/tr_image.o \
			  $(B)/engine/renderer/tr_init.o \
			  $(B)/engine/renderer/tr_light.o \
			  $(B)/engine/renderer/tr_main.o \
			  $(B)/engine/renderer/tr_marks.o \
			  $(B)/engine/renderer/tr_mesh.o \
			  $(B)/engine/renderer/tr_model.o \
			  $(B)/engine/renderer/tr_noise.o \
			  $(B)/engine/renderer/tr_quicksprite.o \
			  $(B)/engine/renderer/tr_scene.o \
			  $(B)/engine/renderer/tr_shade.o \
			  $(B)/engine/renderer/tr_shade_calc.o \
			  $(B)/engine/renderer/tr_shader.o \
			  $(B)/engine/renderer/tr_shadows.o \
			  $(B)/engine/renderer/tr_sky.o \
			  $(B)/engine/renderer/tr_surface.o \
			  $(B)/engine/renderer/tr_surfacesprites.o \
			  $(B)/engine/renderer/tr_terrain.o \
			  $(B)/engine/renderer/tr_world.o \
			  $(B)/engine/jpeg-8c/jaricom.o \
			  $(B)/engine/jpeg-8c/jcapimin.o \
			  $(B)/engine/jpeg-8c/jcapistd.o \
			  $(B)/engine/jpeg-8c/jcarith.o \
			  $(B)/engine/jpeg-8c/jccoefct.o \
			  $(B)/engine/jpeg-8c/jccolor.o \
			  $(B)/engine/jpeg-8c/jcdctmgr.o \
			  $(B)/engine/jpeg-8c/jchuff.o \
			  $(B)/engine/jpeg-8c/jcinit.o \
			  $(B)/engine/jpeg-8c/jcmainct.o \
			  $(B)/engine/jpeg-8c/jcmarker.o \
			  $(B)/engine/jpeg-8c/jcmaster.o \
			  $(B)/engine/jpeg-8c/jcomapi.o \
			  $(B)/engine/jpeg-8c/jcparam.o \
			  $(B)/engine/jpeg-8c/jcprepct.o \
			  $(B)/engine/jpeg-8c/jcsample.o \
			  $(B)/engine/jpeg-8c/jctrans.o \
			  $(B)/engine/jpeg-8c/jdapimin.o \
			  $(B)/engine/jpeg-8c/jdapistd.o \
			  $(B)/engine/jpeg-8c/jdarith.o \
			  $(B)/engine/jpeg-8c/jdatadst.o \
			  $(B)/engine/jpeg-8c/jdatasrc.o \
			  $(B)/engine/jpeg-8c/jdcoefct.o \
			  $(B)/engine/jpeg-8c/jdcolor.o \
			  $(B)/engine/jpeg-8c/jddctmgr.o \
			  $(B)/engine/jpeg-8c/jdhuff.o \
			  $(B)/engine/jpeg-8c/jdinput.o \
			  $(B)/engine/jpeg-8c/jdmainct.o \
			  $(B)/engine/jpeg-8c/jdmarker.o \
			  $(B)/engine/jpeg-8c/jdmaster.o \
			  $(B)/engine/jpeg-8c/jdmerge.o \
			  $(B)/engine/jpeg-8c/jdpostct.o \
			  $(B)/engine/jpeg-8c/jdsample.o \
			  $(B)/engine/jpeg-8c/jdtrans.o \
			  $(B)/engine/jpeg-8c/jerror.o \
			  $(B)/engine/jpeg-8c/jfdctflt.o \
			  $(B)/engine/jpeg-8c/jfdctfst.o \
			  $(B)/engine/jpeg-8c/jfdctint.o \
			  $(B)/engine/jpeg-8c/jidctflt.o \
			  $(B)/engine/jpeg-8c/jidctfst.o \
			  $(B)/engine/jpeg-8c/jidctint.o \
			  $(B)/engine/jpeg-8c/jmemmgr.o \
			  $(B)/engine/jpeg-8c/jmemnobs.o \
			  $(B)/engine/jpeg-8c/jquant1.o \
			  $(B)/engine/jpeg-8c/jquant2.o \
			  $(B)/engine/jpeg-8c/jutils.o \
			  $(B)/engine/png/png.o \
			  $(B)/engine/ghoul2/G2_API.o \
			  $(B)/engine/ghoul2/G2_bolts.o \
			  $(B)/engine/ghoul2/G2_bones.o \
			  $(B)/engine/ghoul2/G2_misc.o \
			  $(B)/engine/ghoul2/G2_surfaces.o \
			  $(B)/engine/RMG/RM_Area.o \
			  $(B)/engine/RMG/RM_Instance.o \
			  $(B)/engine/RMG/RM_InstanceFile.o \
			  $(B)/engine/RMG/RM_Instance_BSP.o \
			  $(B)/engine/RMG/RM_Instance_Group.o \
			  $(B)/engine/RMG/RM_Instance_Random.o \
			  $(B)/engine/RMG/RM_Instance_Void.o \
			  $(B)/engine/RMG/RM_Manager.o \
			  $(B)/engine/RMG/RM_Mission.o \
			  $(B)/engine/RMG/RM_Objective.o \
			  $(B)/engine/RMG/RM_Path.o \
			  $(B)/engine/RMG/RM_Terrain.o \
			  $(B)/engine/icarus/BlockStream.o \
			  $(B)/engine/icarus/IcarusImplementation.o \
			  $(B)/engine/icarus/Sequence.o \
			  $(B)/engine/icarus/Sequencer.o \
			  $(B)/engine/icarus/TaskManager.o \
			  $(B)/engine/zlib/ioapi.o \
			  $(B)/engine/zlib/adler32.o \
			  $(B)/engine/zlib/compress.o \
			  $(B)/engine/zlib/crc32.o \
			  $(B)/engine/zlib/deflate.o \
			  $(B)/engine/zlib/gzclose.o \
			  $(B)/engine/zlib/gzlib.o \
			  $(B)/engine/zlib/gzread.o \
			  $(B)/engine/zlib/gzwrite.o \
			  $(B)/engine/zlib/infback.o \
			  $(B)/engine/zlib/inffast.o \
			  $(B)/engine/zlib/inflate.o \
			  $(B)/engine/zlib/inftrees.o \
			  $(B)/engine/zlib/trees.o \
			  $(B)/engine/zlib/uncompr.o \
			  $(B)/engine/zlib/zutil.o \
			  $(B)/engine/client/vmachine.o \
			  $(B)/engine/ui/ui_atoms.o \
			  $(B)/engine/ui/ui_connect.o \
			  $(B)/engine/ui/ui_debug.o \
			  $(B)/engine/ui/ui_main.o \
			  $(B)/engine/ui/ui_saber.o \
			  $(B)/engine/ui/ui_shared.o \
			  $(B)/engine/ui/ui_syscalls.o \
			  $(B)/engine/game/Q3_Interface.o

DEDICATED_NAME		= $(B)/$(PLATFORM)jampded
DEDICATED_CFLAGS	+= -m32 -fpermissive -w -DDEDICATED -O2 -unroll -D_JK2 -DNDEBUG -DC_ONLY -DFINAL_BUILD -D_M_IX86 -I.
DEDICATED_LDFLAGS	= -m32 -ldl
DEDICATED_OBJS		= $(B)/dedicated/server/sv_bot.o \
			  $(B)/dedicated/server/sv_client.o \
			  $(B)/dedicated/server/sv_ccmds.o \
			  $(B)/dedicated/server/sv_game.o \
			  $(B)/dedicated/server/sv_init.o \
			  $(B)/dedicated/server/sv_main.o \
			  $(B)/dedicated/server/sv_net_chan.o \
			  $(B)/dedicated/server/sv_snapshot.o \
			  $(B)/dedicated/server/sv_world.o \
			  $(B)/dedicated/qcommon/cm_load.o \
			  $(B)/dedicated/qcommon/stringed_ingame.o \
			  $(B)/dedicated/qcommon/stringed_interface.o \
			  $(B)/dedicated/qcommon/GenericParser2.o \
			  $(B)/dedicated/qcommon/cm_patch.o \
			  $(B)/dedicated/qcommon/cm_polylib.o \
			  $(B)/dedicated/qcommon/cm_test.o \
			  $(B)/dedicated/qcommon/cm_trace.o \
			  $(B)/dedicated/qcommon/common.o \
			  $(B)/dedicated/qcommon/cvar.o \
			  $(B)/dedicated/qcommon/md4.o \
			  $(B)/dedicated/qcommon/msg.o \
			  $(B)/dedicated/qcommon/net_chan.o \
			  $(B)/dedicated/qcommon/huffman.o \
			  $(B)/dedicated/qcommon/q_math.o \
			  $(B)/dedicated/qcommon/q_shared.o \
			  $(B)/dedicated/qcommon/z_memman_pc.o \
			  $(B)/dedicated/zlib/ioapi.o \
			  $(B)/dedicated/qcommon/unzip.o \
			  $(B)/dedicated/qcommon/vm.o \
			  $(B)/dedicated/qcommon/vm_interpreted.o \
			  $(B)/dedicated/botlib/be_aas_bspq3.o \
			  $(B)/dedicated/botlib/be_aas_cluster.o \
			  $(B)/dedicated/botlib/be_aas_debug.o \
			  $(B)/dedicated/botlib/be_aas_entity.o \
			  $(B)/dedicated/botlib/be_aas_file.o \
			  $(B)/dedicated/botlib/be_aas_main.o \
			  $(B)/dedicated/botlib/be_aas_move.o \
			  $(B)/dedicated/botlib/be_aas_optimize.o \
			  $(B)/dedicated/botlib/be_aas_reach.o \
			  $(B)/dedicated/botlib/be_aas_route.o \
			  $(B)/dedicated/botlib/be_aas_routealt.o \
			  $(B)/dedicated/botlib/be_aas_sample.o \
			  $(B)/dedicated/botlib/be_ai_char.o \
			  $(B)/dedicated/botlib/be_ai_chat.o \
			  $(B)/dedicated/botlib/be_ai_gen.o \
			  $(B)/dedicated/botlib/be_ai_goal.o \
			  $(B)/dedicated/botlib/be_ai_move.o \
			  $(B)/dedicated/botlib/be_ai_weap.o \
			  $(B)/dedicated/botlib/be_ai_weight.o \
			  $(B)/dedicated/botlib/be_ea.o \
			  $(B)/dedicated/botlib/be_interface.o \
			  $(B)/dedicated/botlib/l_crc.o \
			  $(B)/dedicated/botlib/l_libvar.o \
			  $(B)/dedicated/botlib/l_log.o \
			  $(B)/dedicated/botlib/l_memory.o \
			  $(B)/dedicated/botlib/l_precomp.o \
			  $(B)/dedicated/botlib/l_script.o \
			  $(B)/dedicated/botlib/l_struct.o \
			  $(B)/dedicated/unix_ded/linux_common.o \
			  $(B)/dedicated/unix_ded/unix_main.o \
			  $(B)/dedicated/unix_ded/unix_net.o \
			  $(B)/dedicated/unix_ded/unix_shared.o \
			  $(B)/dedicated/unix/snapvector.o \
			  $(B)/dedicated/unix/vm_x86.o \
			  $(B)/dedicated/ghoul2/G2_API.o \
			  $(B)/dedicated/ghoul2/G2_bolts.o \
			  $(B)/dedicated/ghoul2/G2_surfaces.o \
			  $(B)/dedicated/ghoul2/G2_misc.o \
			  $(B)/dedicated/null/null_client.o \
			  $(B)/dedicated/null/null_input.o \
			  $(B)/dedicated/null/null_snddma.o \
			  $(B)/dedicated/null/null_glimp.o \
			  $(B)/dedicated/null/null_renderer.o \
			  $(B)/dedicated/icarus/BlockStream.o \
			  $(B)/dedicated/icarus/GameInterface.o \
			  $(B)/dedicated/icarus/Instance.o \
			  $(B)/dedicated/icarus/Interface.o \
			  $(B)/dedicated/icarus/Memory.o \
			  $(B)/dedicated/icarus/Q3_Interface.o \
			  $(B)/dedicated/icarus/Q3_Registers.o \
			  $(B)/dedicated/icarus/Sequence.o \
			  $(B)/dedicated/icarus/Sequencer.o \
			  $(B)/dedicated/icarus/TaskManager.o \
			  $(B)/dedicated/renderer/tr_model.o \
			  $(B)/dedicated/renderer/tr_image.o \
			  $(B)/dedicated/qcommon/RoffSystem.o \
			  $(B)/dedicated/renderer/tr_ghoul2.o \
			  $(B)/dedicated/renderer/matcomp.o \
			  $(B)/dedicated/renderer/tr_init.o \
			  $(B)/dedicated/renderer/tr_main.o \
			  $(B)/dedicated/renderer/tr_backend.o \
			  $(B)/dedicated/renderer/tr_mesh.o \
			  $(B)/dedicated/ghoul2/G2_bones.o \
			  $(B)/dedicated/renderer/tr_shader.o \
			  $(B)/dedicated/qcommon/cmd_pc.o \
			  $(B)/dedicated/server/NPCNav/navigator.o \
			  $(B)/dedicated/server/NPCNav/gameCallbacks.o \
			  $(B)/dedicated/qcommon/files_common.o \
			  $(B)/dedicated/qcommon/cmd_common.o \
			  $(B)/dedicated/qcommon/files_pc.o \
			  $(B)/dedicated/RMG/RM_Manager.o \
			  $(B)/dedicated/RMG/RM_Mission.o \
			  $(B)/dedicated/RMG/RM_Instance.o \
			  $(B)/dedicated/RMG/RM_InstanceFile.o \
			  $(B)/dedicated/RMG/RM_Instance_BSP.o \
			  $(B)/dedicated/RMG/RM_Instance_Group.o \
			  $(B)/dedicated/RMG/RM_Instance_Void.o \
			  $(B)/dedicated/RMG/RM_Instance_Random.o \
			  $(B)/dedicated/RMG/RM_Objective.o \
			  $(B)/dedicated/RMG/RM_Terrain.o \
			  $(B)/dedicated/RMG/RM_Path.o \
			  $(B)/dedicated/RMG/RM_Area.o \
			  $(B)/dedicated/qcommon/cm_terrain.o \
			  $(B)/dedicated/qcommon/cm_randomterrain.o \
			  $(B)/dedicated/qcommon/cm_shader.o \
			  $(B)/dedicated/jpeg-8c/jaricom.o \
			  $(B)/dedicated/jpeg-8c/jcapimin.o \
			  $(B)/dedicated/jpeg-8c/jcapistd.o \
			  $(B)/dedicated/jpeg-8c/jcarith.o \
			  $(B)/dedicated/jpeg-8c/jccoefct.o \
			  $(B)/dedicated/jpeg-8c/jccolor.o \
			  $(B)/dedicated/jpeg-8c/jcdctmgr.o \
			  $(B)/dedicated/jpeg-8c/jchuff.o \
			  $(B)/dedicated/jpeg-8c/jcinit.o \
			  $(B)/dedicated/jpeg-8c/jcmainct.o \
			  $(B)/dedicated/jpeg-8c/jcmarker.o \
			  $(B)/dedicated/jpeg-8c/jcmaster.o \
			  $(B)/dedicated/jpeg-8c/jcomapi.o \
			  $(B)/dedicated/jpeg-8c/jcparam.o \
			  $(B)/dedicated/jpeg-8c/jcprepct.o \
			  $(B)/dedicated/jpeg-8c/jcsample.o \
			  $(B)/dedicated/jpeg-8c/jctrans.o \
			  $(B)/dedicated/jpeg-8c/jdapimin.o \
			  $(B)/dedicated/jpeg-8c/jdapistd.o \
			  $(B)/dedicated/jpeg-8c/jdarith.o \
			  $(B)/dedicated/jpeg-8c/jdatadst.o \
			  $(B)/dedicated/jpeg-8c/jdatasrc.o \
			  $(B)/dedicated/jpeg-8c/jdcoefct.o \
			  $(B)/dedicated/jpeg-8c/jdcolor.o \
			  $(B)/dedicated/jpeg-8c/jddctmgr.o \
			  $(B)/dedicated/jpeg-8c/jdhuff.o \
			  $(B)/dedicated/jpeg-8c/jdinput.o \
			  $(B)/dedicated/jpeg-8c/jdmainct.o \
			  $(B)/dedicated/jpeg-8c/jdmarker.o \
			  $(B)/dedicated/jpeg-8c/jdmaster.o \
			  $(B)/dedicated/jpeg-8c/jdmerge.o \
			  $(B)/dedicated/jpeg-8c/jdpostct.o \
			  $(B)/dedicated/jpeg-8c/jdsample.o \
			  $(B)/dedicated/jpeg-8c/jdtrans.o \
			  $(B)/dedicated/jpeg-8c/jerror.o \
			  $(B)/dedicated/jpeg-8c/jfdctflt.o \
			  $(B)/dedicated/jpeg-8c/jfdctfst.o \
			  $(B)/dedicated/jpeg-8c/jfdctint.o \
			  $(B)/dedicated/jpeg-8c/jidctflt.o \
			  $(B)/dedicated/jpeg-8c/jidctfst.o \
			  $(B)/dedicated/jpeg-8c/jidctint.o \
			  $(B)/dedicated/jpeg-8c/jmemmgr.o \
			  $(B)/dedicated/jpeg-8c/jmemnobs.o \
			  $(B)/dedicated/jpeg-8c/jquant1.o \
			  $(B)/dedicated/jpeg-8c/jquant2.o \
			  $(B)/dedicated/jpeg-8c/jutils.o \
			  $(B)/dedicated/zlib/adler32.o \
			  $(B)/dedicated/zlib/compress.o \
			  $(B)/dedicated/zlib/crc32.o \
			  $(B)/dedicated/zlib/deflate.o \
			  $(B)/dedicated/zlib/gzclose.o \
			  $(B)/dedicated/zlib/gzlib.o \
			  $(B)/dedicated/zlib/gzread.o \
			  $(B)/dedicated/zlib/gzwrite.o \
			  $(B)/dedicated/zlib/infback.o \
			  $(B)/dedicated/zlib/inffast.o \
			  $(B)/dedicated/zlib/inflate.o \
			  $(B)/dedicated/zlib/inftrees.o \
			  $(B)/dedicated/zlib/trees.o \
			  $(B)/dedicated/zlib/uncompr.o \
			  $(B)/dedicated/zlib/zutil.o

ifeq ($(PLATFORM),darwin)
	DEDICATED_CFLAGS += -DMACOS_X
	ENGINE_CFLAGS += -DMACOS_X
	UI_CFLAGS += -DMACOS_X
	CGAME_CFLAGS += -DMACOS_X
	GAME_CFLAGS += -DMACOS_X
else
	GAME_CFLAGS += -D__linux__
	UI_CFLAGS += -D__linux__
	CGAME_CFLAGS += -D__linux__
endif

all: makedirs engine game cgame ui dedicated

makedirs:
	@if [ ! -d $(B) ];then mkdir $(B);fi
	@if [ ! -d $(B)/dedicated ];then mkdir $(B)/dedicated;fi
	@if [ ! -d $(B)/dedicated/botlib ];then mkdir $(B)/dedicated/botlib;fi
	@if [ ! -d $(B)/dedicated/unix ];then mkdir $(B)/dedicated/unix;fi
	@if [ ! -d $(B)/dedicated/unix_ded ];then mkdir $(B)/dedicated/unix_ded;fi
	@if [ ! -d $(B)/dedicated/ghoul2 ];then mkdir $(B)/dedicated/ghoul2;fi
	@if [ ! -d $(B)/dedicated/null ];then mkdir $(B)/dedicated/null;fi
	@if [ ! -d $(B)/dedicated/icarus ];then mkdir $(B)/dedicated/icarus;fi
	@if [ ! -d $(B)/dedicated/jpeg-8c ];then mkdir $(B)/dedicated/jpeg-8c;fi
	@if [ ! -d $(B)/dedicated/ghoul2 ];then mkdir $(B)/dedicated/ghoul2;fi
	@if [ ! -d $(B)/dedicated/renderer ];then mkdir $(B)/dedicated/renderer;fi
	@if [ ! -d $(B)/dedicated/server ];then mkdir $(B)/dedicated/server;fi
	@if [ ! -d $(B)/dedicated/server/NPCNav ];then mkdir $(B)/dedicated/server/NPCNav;fi
	@if [ ! -d $(B)/dedicated/qcommon ];then mkdir $(B)/dedicated/qcommon;fi
	@if [ ! -d $(B)/dedicated/RMG ];then mkdir $(B)/dedicated/RMG;fi
	@if [ ! -d $(B)/dedicated/zlib ];then mkdir $(B)/dedicated/zlib;fi
	@if [ ! -d $(B)/engine ];then mkdir $(B)/engine;fi
	@if [ ! -d $(B)/engine/botlib ];then mkdir $(B)/engine/botlib;fi
	@if [ ! -d $(B)/engine/client ];then mkdir $(B)/engine/client;fi
	@if [ ! -d $(B)/engine/ghoul2 ];then mkdir $(B)/engine/ghoul2;fi
	@if [ ! -d $(B)/engine/icarus ];then mkdir $(B)/engine/icarus;fi
	@if [ ! -d $(B)/engine/jpeg-8c ];then mkdir $(B)/engine/jpeg-8c;fi
	@if [ ! -d $(B)/engine/mp3code ];then mkdir $(B)/engine/mp3code;fi
	@if [ ! -d $(B)/engine/png ];then mkdir $(B)/engine/png;fi
	@if [ ! -d $(B)/engine/qcommon ];then mkdir $(B)/engine/qcommon;fi
	@if [ ! -d $(B)/engine/RMG ];then mkdir $(B)/engine/RMG;fi
	@if [ ! -d $(B)/engine/renderer ];then mkdir $(B)/engine/renderer;fi
	@if [ ! -d $(B)/engine/sdl ];then mkdir $(B)/engine/sdl;fi
	@if [ ! -d $(B)/engine/server ];then mkdir $(B)/engine/server;fi
	@if [ ! -d $(B)/engine/server/NPCNav ];then mkdir $(B)/engine/server/NPCNav;fi
	@if [ ! -d $(B)/engine/sys ];then mkdir $(B)/engine/sys;fi
	@if [ ! -d $(B)/engine/unix ];then mkdir $(B)/engine/unix;fi
	@if [ ! -d $(B)/engine/unix_ded ];then mkdir $(B)/engine/unix_ded;fi
	@if [ ! -d $(B)/engine/zlib ];then mkdir $(B)/engine/zlib;fi
	@if [ ! -d $(B)/cgame ];then mkdir $(B)/cgame;fi
	@if [ ! -d $(B)/game ];then mkdir $(B)/game;fi
	@if [ ! -d $(B)/ui ];then mkdir $(B)/ui;fi

#
# GAME RULES
#

game: $(GAME_NAME)

$(GAME_NAME): $(GAME_OBJS)
	$(CXX) -o $(GAME_NAME) $(GAME_OBJS) $(GAME_LDFLAGS)

$(B)/game/q_%.o: qcommon/q_%.cpp
	$(CC) $(GAME_CFLAGS) -fPIC -c $< -o $@

$(B)/%.o: %.cpp
	$(CC) $(GAME_CFLAGS) -fPIC -c $< -o $@


#
# CGAME RULES
#

cgame: $(CGAME_NAME)

$(CGAME_NAME): $(CGAME_OBJS)
	$(CC) -o $(CGAME_NAME) $(CGAME_OBJS) $(CGAME_LDFLAGS)

$(B)/cgame/q_%.o: qcommon/q_%.c
	$(CC) $(CGAME_CFLAGS) -fPIC -c $< -o $@

$(B)/cgame/%NPC.o: game/%NPC.c
	$(CC) $(CGAME_CFLAGS) -fPIC -c $< -o $@

$(B)/cgame/ui_%.o: ui/ui_%.c
	$(CC) $(CGAME_CFLAGS) -fPIC -c $< -o $@

$(B)/cgame/bg_%.o: game/bg_%.c
	$(CC) $(CGAME_CFLAGS) -fPIC -c $< -o $@

$(B)/cgame/%.o: cgame/%.c
	$(CC) $(CGAME_CFLAGS) -fPIC -c $< -o $@

#
# UI RULES
#

ui: $(UI_NAME)

$(UI_NAME): $(UI_OBJS)
	$(CC) -o $(UI_NAME) $(UI_OBJS) $(UI_LDFLAGS)

$(B)/ui/q_%.o: qcommon/q_%.c
	$(CC) $(UI_CFLAGS) -fPIC -c $< -o $@

$(B)/ui/bg_%.o: game/bg_%.c
	$(CC) $(UI_CFLAGS) -fPIC -c $< -o $@

$(B)/ui/%.o: ui/%.c
	$(CC) $(UI_CFLAGS) -fPIC -c $< -o $@

#
# ENGINE RULES
#

engine: $(ENGINE_NAME)

$(ENGINE_NAME): $(ENGINE_OBJS)
	$(CXX) -o $(ENGINE_NAME) $(ENGINE_OBJS) $(ENGINE_LDFLAGS)

$(B)/engine/zlib/%.o: zlib/%.c
	$(CC) $(ENGINE_CFLAGS) -c $< -o $@

$(B)/engine/jpeg-8c/%.o: jpeg-8c/%.c
	$(CC) $(ENGINE_CFLAGS) -c $< -o $@

$(B)/engine/mp3code/%.o: mp3code/%.c
	$(CC) $(ENGINE_CFLAGS) -c $< -o $@

$(B)/engine/botlib/%.o: botlib/%.cpp
	$(CXX) $(ENGINE_CFLAGS) -DBOTLIB -c $< -o $@

$(B)/engine/unix/%.o: unix/%.nasm
	nasm -f $(BINARY_FMT) -o $@  $<

$(B)/engine/%.o: %.c
	$(CXX) $(ENGINE_CFLAGS) -c $< -o $@

$(B)/engine/%.o: %.cpp
	$(CXX) $(ENGINE_CFLAGS) -c $< -o $@

#
# DEDICATED RULES
#

dedicated: $(DEDICATED_NAME)

$(DEDICATED_NAME): $(DEDICATED_OBJS)
	$(CXX) -o $(DEDICATED_NAME) $(DEDICATED_OBJS) $(DEDICATED_LDFLAGS)

$(B)/dedicated/zlib/%.o: zlib/%.c
	$(CC) $(DEDICATED_CFLAGS) -c $< -o $@

$(B)/dedicated/jpeg-8c/%.o: jpeg-8c/%.c
	$(CC) $(DEDICATED_CFLAGS) -c $< -o $@

$(B)/dedicated/mp3code/%.o: mp3code/%.c
	$(CC) $(DEDICATED_CFLAGS) -c $< -o $@

$(B)/dedicated/botlib/%.o: botlib/%.cpp
	$(CXX) $(DEDICATED_CFLAGS) -DBOTLIB -c $< -o $@

$(B)/dedicated/unix/%.o: unix/%.nasm
	nasm -f $(BINARY_FMT) -o $@  $<

$(B)/dedicated/%.o: %.c
	$(CXX) $(DEDICATED_CFLAGS) -c $< -o $@

$(B)/dedicated/%.o: %.cpp
	$(CXX) $(DEDICATED_CFLAGS) -c $< -o $@

clean:
	$(RM) $(ENGINE_OBJS) $(GAME_OBJS) $(CGAME_OBJS) $(UI_OBJS) $(DEDICATED_OBJS) \
	$(ENGINE_NAME) $(GAME_NAME) $(CGAME_NAME) $(UI_NAME) $(DEDICATED_NAME)