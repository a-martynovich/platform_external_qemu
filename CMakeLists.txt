cmake_minimum_required (VERSION 3.1)

project(QEMU VERSION 1.0)

add_executable(emulator
        android/android-constants.c
        android/async-console.c
        android/async-utils.c
        android/framebuffer.c
        android/iolooper.cpp
        android/avd/hw-config.c
        android/avd/info.c
        android/avd/scanner.c
        android/avd/util.c
        android/sockets.c
        android/sync-utils.c
        android/base/async/AsyncReader.cpp
        android/base/async/AsyncWriter.cpp
        android/base/async/Looper.cpp
        android/base/async/ThreadLooper.cpp
        android/base/containers/PodVector.cpp
        android/base/containers/PointerSet.cpp
        android/base/containers/HashUtils.cpp
        android/base/containers/StringVector.cpp
        android/base/files/PathUtils.cpp
        android/base/misc/HttpUtils.cpp
        android/base/misc/StringUtils.cpp
        android/base/misc/Utf8Utils.cpp
        android/base/sockets/SocketDrainer.cpp
        android/base/sockets/SocketUtils.cpp
        android/base/sockets/SocketWaiter.cpp
        android/base/synchronization/MessageChannel.cpp
        android/base/Log.cpp
        android/base/memory/LazyInstance.cpp
        android/base/String.cpp
        android/base/StringFormat.cpp
        android/base/StringView.cpp
        android/base/system/System.cpp
        android/base/threads/ThreadStore.cpp
        android/emulation/CpuAccelerator.cpp
        android/filesystems/ext4_utils.cpp
        android/filesystems/fstab_parser.cpp
        android/filesystems/partition_types.cpp
        android/filesystems/ramdisk_extractor.cpp
        android/kernel/kernel_utils.cpp
        android/qemu/base/async/Looper.cpp
        android/looper-base.cpp
        android/looper-generic.cpp
        android/opengl/EmuglBackendList.cpp
        android/opengl/EmuglBackendScanner.cpp
        android/opengl/emugl_config.cpp
        android/opengl/GpuFrameBridge.cpp
        android/utils/aconfig-file.c
        android/utils/assert.c
        android/utils/bufprint.c
        android/utils/debug.c
        android/utils/dll.c
        android/utils/dirscanner.cpp
        android/utils/eintr_wrapper.c
        android/utils/filelock.c
        android/utils/file_data.c
        android/utils/format.cpp
        android/utils/host_bitness.cpp
        android/utils/http_utils.cpp
        android/utils/ini.c
        android/utils/intmap.c
        android/utils/lineinput.c
        android/utils/mapfile.c
        android/utils/misc.c
        android/utils/panic.c
        android/utils/path.c
        android/utils/property_file.c
        android/utils/reflist.c
        android/utils/refset.c
        android/utils/socket_drainer.cpp
        android/utils/stralloc.c
        android/utils/string.cpp
        android/utils/system.c
        android/utils/tempfile.c
        android/utils/uncompress.cpp
        android/utils/utf8_utils.cpp
        android/utils/vector.c
        android/utils/win32_cmdline_quote.c
        android/utils/x86_cpuid.c
        android/loadpng.c
        android/gpu_frame.cpp
        android/emulator-window.c
        android/resource.c
        android/user-config.c
#        android/main-emulator.c
        tcg/optimize.c
        tcg/tcg.c
        tcg-runtime.c
        util/bitops.c
        util/host-utils.c
        backends/msmouse.c
        cpu-exec.c
        cputlb.c
        exec.c
        main-loop.c
        memory-android.c
        monitor-android.c
        translate-all.c
        code-profile.c
        target-i386/cc_helper.c
        target-i386/excp_helper.c
        target-i386/fpu_helper.c
        target-i386/int_helper.c
        target-i386/mem_helper.c
        target-i386/misc_helper.c
        target-i386/seg_helper.c
        target-i386/smm_helper.c
        target-i386/svm_helper.c
        target-i386/helper.c
        target-i386/translate.c
        target-i386/machine.c
        target-i386/hax-all.c
        fpu/softfloat.c
        cpus.c
        arch_init.c
        audio/audio.c
        disas.c
        dma-helpers.c
        gdbstub.c
        qemu-timer.c
        log-rotate-android.c
        vl-android.c
        android/cmdline-option.c
        android/console.c
        android/cpu_accelerator.cpp
        android/display.c
        android/display-core.c
        android/help.c
        android/main-common.c
        android/main-common-ui.c
        android/main.c
        android/opengles.c
        android/user-events-qemu.c
        hw/core/loader.c
        util/bitmap.c
        util/bitops.c
        ui/keymaps.c
        util/qemu-timer-common.c
        util/iov.c

# HW    hw/
        hw/core/irq.c
        hw/core/qdev.c
        hw/core/sysbus.c
        hw/core/dma.c
        hw/android/goldfish/audio.c
        hw/android/goldfish/device.c
        hw/android/goldfish/events_device.c
        hw/android/goldfish/fb.c
        hw/android/goldfish/battery.c
        hw/android/goldfish/mmc.c
        hw/android/goldfish/nand.c
        hw/android/goldfish/pipe.c
        hw/android/goldfish/tty.c
        hw/android/goldfish/vmem.c
        hw/android/goldfish/trace.c
        hw/android/goldfish/profile.c
        hw/pci/pci.c
        hw/watchdog/watchdog.c
        hw/intc/apic.c
        hw/intc/i8259.c
        hw/timer/mc146818rtc.c
        hw/pci-host/piix.c
        hw/timer/i8254.c
        hw/input/pckbd.c
        hw/intc/ioapic.c
        hw/input/ps2.c
        hw/i386/smbios.c
        hw/nvram/fw_cfg.c
        hw/net/ne2000.c
        hw/i386/pc.c

# SKIN  android/skin/
        android/skin/charmap.c
        android/skin/rect.c
        android/skin/region.c
        android/skin/image.c
        android/skin/trackball.c
        android/skin/keyboard.c
        android/skin/keycode.c
        android/skin/keycode-buffer.c
        android/skin/keyset.c
        android/skin/file.c
        android/skin/window.c
        android/skin/resource.c
        android/skin/scaler.c
        android/skin/ui.c
        android/skin/event-sdl2.c
        android/skin/surface-sdl2.c
        android/skin/winsys-sdl2.c

# AUDIO audio
        audio/noaudio.c
        audio/wavaudio.c
        audio/wavcapture.c
        audio/mixeng.c

# MISC
        aio-android.c
        async.c
        iohandler.c
        ioport.c
        migration-dummy-android.c
        qemu-char.c
        qemu-log.c
        savevm.c
        android/boot-properties.c
        android/cbuffer.c
        android/charpipe.c
        android/core-init-utils.c
        android/gps.c
        android/hw-kmsg.c
        android/hw-lcd.c
        android/hw-events.c
        android/hw-control.c
        android/hw-fingerprint.c
        android/hw-sensors.c
        android/hw-qemud.c
        android/looper-qemu.cpp
        android/hw-pipe-net.c
        android/qemu/base/async/Looper.cpp
        android/qemu-setup.c
        android/qemu-tcpdump.c
        android/shaper.c
        android/snapshot.c
        android/async-socket-connector.c
        android/async-socket.c
        android/sdk-controller-socket.c
        android/sensors-port.c
        android/utils/timezone.c
        android/camera/camera-format-converters.c
        android/camera/camera-service.c
        android/adb-server.c
        android/adb-qemud.c
        android/snaphost-android.c
        android/multitouch-screen.c
        android/multitouch-port.c
        android/utils/jpeg-compress.c
        net/net-android.c
        qobject/qerror.c
#        qom/container.c
#        qom/object.c
#        qom/qom-qobject.c
        ui/console.c
        ui/d3des.c
        ui/input.c
        ui/vnc-android.c
        util/aes.c
        util/cutils.c
        util/error.c
        util/hexdump.c
        util/iov.c
        util/module.c
        util/notify.c
        util/osdep.c
        util/path.c
        util/qemu-config.c
        util/qemu-error.c
        util/qemu-option.c
        util/qemu-sockets-android.c
        util/unicode.c
        util/yield-android.c
        disas/i386.c

# SLIRP slirp-android/
        slirp-android/bootp.c
        slirp-android/cksum.c
        slirp-android/debug.c
        slirp-android/if.c
        slirp-android/ip_icmp.c
        slirp-android/ip_input.c
        slirp-android/ip_output.c
        slirp-android/mbuf.c
        slirp-android/misc.c
        slirp-android/sbuf.c
        slirp-android/slirp.c
        slirp-android/socket.c
        slirp-android/tcp_input.c
        slirp-android/tcp_output.c
        slirp-android/tcp_subr.c
        slirp-android/tcp_timer.c
        slirp-android/tftp.c
        slirp-android/udp.c

# PROXY proxy/
        proxy/proxy_common.c
        proxy/proxy_http.c
        proxy/proxy_http_connector.c
        proxy/proxy_http_rewriter.c

# TELEPHONY telephony/
        telephony/android_modem.c
        telephony/modem_driver.c
        telephony/gsm.c
        telephony/sim_card.c
        telephony/sysdeps_qemu.c
        telephony/sms.c
        telephony/remote_call.c

# QOBJECT
        qobject/json-lexer.c
        qobject/json-parser.c
        qobject/json-streamer.c
        qobject/qjson.c
        qobject/qbool.c
        qobject/qdict.c
        qobject/qfloat.c
        qobject/qint.c
        qobject/qlist.c
        qobject/qstring.c

# BLOCK block
        block.c
        blockdev.c
        block/qcow2.c
        block/qcow2-refcount.c
        block/qcow2-snapshot.c
        block/qcow2-cluster.c
        block/raw.c

# LIBSPARSE distrib/libsparse
        distrib/libsparse/src/backed_block.c
        distrib/libsparse/src/output_file.c
        distrib/libsparse/src/sparse.c
        distrib/libsparse/src/sparse_crc32.c
        distrib/libsparse/src/sparse_err.c
        distrib/libsparse/src/sparse_read.c
#        distrib/libsparse/src/img2simg.c

# SDL2
        distrib/sdl2-2.0.3/src/SDL_assert.c
        distrib/sdl2-2.0.3/src/SDL.c
        distrib/sdl2-2.0.3/src/SDL_error.c
        distrib/sdl2-2.0.3/src/SDL_hints.c
        distrib/sdl2-2.0.3/src/SDL_log.c
        distrib/sdl2-2.0.3/src/atomic/SDL_atomic.c
        distrib/sdl2-2.0.3/src/atomic/SDL_spinlock.c
        distrib/sdl2-2.0.3/src/events/SDL_clipboardevents.c
        distrib/sdl2-2.0.3/src/events/SDL_dropevents.c
        distrib/sdl2-2.0.3/src/events/SDL_events.c
        distrib/sdl2-2.0.3/src/events/SDL_gesture.c
        distrib/sdl2-2.0.3/src/events/SDL_keyboard.c
        distrib/sdl2-2.0.3/src/events/SDL_mouse.c
        distrib/sdl2-2.0.3/src/events/SDL_quit.c
        distrib/sdl2-2.0.3/src/events/SDL_touch.c
        distrib/sdl2-2.0.3/src/events/SDL_windowevents.c
        distrib/sdl2-2.0.3/src/file/SDL_rwops.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_getenv.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_iconv.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_malloc.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_qsort.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_stdlib.c
        distrib/sdl2-2.0.3/src/stdlib/SDL_string.c
        distrib/sdl2-2.0.3/src/cpuinfo/SDL_cpuinfo.c
        distrib/sdl2-2.0.3/src/thread/SDL_thread.c
# src/libm
        distrib/sdl2-2.0.3/src/libm/e_atan2.c
        distrib/sdl2-2.0.3/src/libm/e_log.c
        distrib/sdl2-2.0.3/src/libm/e_pow.c
        distrib/sdl2-2.0.3/src/libm/e_rem_pio2.c
        distrib/sdl2-2.0.3/src/libm/e_sqrt.c
        distrib/sdl2-2.0.3/src/libm/k_cos.c
        distrib/sdl2-2.0.3/src/libm/k_rem_pio2.c
        distrib/sdl2-2.0.3/src/libm/k_sin.c
        distrib/sdl2-2.0.3/src/libm/s_atan.c
        distrib/sdl2-2.0.3/src/libm/s_copysign.c
        distrib/sdl2-2.0.3/src/libm/s_cos.c
        distrib/sdl2-2.0.3/src/libm/s_fabs.c
        distrib/sdl2-2.0.3/src/libm/s_floor.c
        distrib/sdl2-2.0.3/src/libm/s_scalbn.c
        distrib/sdl2-2.0.3/src/libm/s_sin.c
# src/dynapi
        distrib/sdl2-2.0.3/src/dynapi/SDL_dynapi.c
# src/thread
        distrib/sdl2-2.0.3/src/timer/SDL_timer.c
# src/video
        distrib/sdl2-2.0.3/src/video/SDL_blit_0.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_1.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_A.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_auto.c
        distrib/sdl2-2.0.3/src/video/SDL_blit.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_copy.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_N.c
        distrib/sdl2-2.0.3/src/video/SDL_blit_slow.c
        distrib/sdl2-2.0.3/src/video/SDL_bmp.c
        distrib/sdl2-2.0.3/src/video/SDL_clipboard.c
        distrib/sdl2-2.0.3/src/video/SDL_fillrect.c
        distrib/sdl2-2.0.3/src/video/SDL_pixels.c
        distrib/sdl2-2.0.3/src/video/SDL_rect.c
        distrib/sdl2-2.0.3/src/video/SDL_RLEaccel.c
        distrib/sdl2-2.0.3/src/video/SDL_shape.c
        distrib/sdl2-2.0.3/src/video/SDL_stretch.c
        distrib/sdl2-2.0.3/src/video/SDL_surface.c
        distrib/sdl2-2.0.3/src/video/SDL_video.c
        distrib/sdl2-2.0.3/src/video/dummy/SDL_nullevents.c
        distrib/sdl2-2.0.3/src/video/dummy/SDL_nullframebuffer.c
        distrib/sdl2-2.0.3/src/video/dummy/SDL_nullvideo.c
        distrib/sdl2-2.0.3/src/video/SDL_egl.c
# src/render
        distrib/sdl2-2.0.3/src/render/SDL_d3dmath.c
        distrib/sdl2-2.0.3/src/render/SDL_render.c
        distrib/sdl2-2.0.3/src/render/SDL_yuv_mmx.c
        distrib/sdl2-2.0.3/src/render/SDL_yuv_sw.c
        distrib/sdl2-2.0.3/src/render/software/SDL_blendfillrect.c
        distrib/sdl2-2.0.3/src/render/software/SDL_blendline.c
        distrib/sdl2-2.0.3/src/render/software/SDL_blendpoint.c
        distrib/sdl2-2.0.3/src/render/software/SDL_drawline.c
        distrib/sdl2-2.0.3/src/render/software/SDL_drawpoint.c
        distrib/sdl2-2.0.3/src/render/software/SDL_render_sw.c
        distrib/sdl2-2.0.3/src/render/software/SDL_rotate.c
        distrib/sdl2-2.0.3/src/render/opengl/SDL_render_gl.c
        distrib/sdl2-2.0.3/src/render/opengl/SDL_shaders_gl.c
        distrib/sdl2-2.0.3/src/render/direct3d/SDL_render_d3d.c # ???
        distrib/sdl2-2.0.3/src/render/opengles2/SDL_render_gles2.c
        distrib/sdl2-2.0.3/src/render/opengles2/SDL_shaders_gles2.c
# src/joystick
        distrib/sdl2-2.0.3/src/joystick/SDL_gamecontroller.c
        distrib/sdl2-2.0.3/src/joystick/SDL_joystick.c
# src/haptic
        distrib/sdl2-2.0.3/src/haptic/SDL_haptic.c
# src/audio
        distrib/sdl2-2.0.3/src/audio/SDL_audio.c
        distrib/sdl2-2.0.3/src/audio/SDL_audiocvt.c
        distrib/sdl2-2.0.3/src/audio/SDL_audiotypecvt.c
        distrib/sdl2-2.0.3/src/audio/SDL_mixer.c
        distrib/sdl2-2.0.3/src/audio/dummy/SDL_dummyaudio.c
        distrib/sdl2-2.0.3/src/audio/disk/SDL_diskaudio.c

# ZLIB  distrib/zlib-1.2.8
        distrib/zlib-1.2.8/adler32.c
        distrib/zlib-1.2.8/compress.c
        distrib/zlib-1.2.8/crc32.c
        distrib/zlib-1.2.8/deflate.c
        distrib/zlib-1.2.8/gzclose.c
        distrib/zlib-1.2.8/gzlib.c
        distrib/zlib-1.2.8/gzread.c
        distrib/zlib-1.2.8/gzwrite.c
        distrib/zlib-1.2.8/infback.c
        distrib/zlib-1.2.8/inffast.c
        distrib/zlib-1.2.8/inflate.c
        distrib/zlib-1.2.8/inftrees.c
        distrib/zlib-1.2.8/trees.c
        distrib/zlib-1.2.8/uncompr.c
        distrib/zlib-1.2.8/zutil.c

# JPEG  distrib/jpeg-6b
        distrib/jpeg-6b/jcapimin.c
        distrib/jpeg-6b/jcapistd.c
        distrib/jpeg-6b/jccoefct.c
        distrib/jpeg-6b/jccolor.c
        distrib/jpeg-6b/jcdctmgr.c
        distrib/jpeg-6b/jchuff.c
        distrib/jpeg-6b/jcinit.c
        distrib/jpeg-6b/jcmainct.c
        distrib/jpeg-6b/jcmarker.c
        distrib/jpeg-6b/jcmaster.c
        distrib/jpeg-6b/jcomapi.c
        distrib/jpeg-6b/jcparam.c
        distrib/jpeg-6b/jcphuff.c
        distrib/jpeg-6b/jcprepct.c
        distrib/jpeg-6b/jcsample.c
        distrib/jpeg-6b/jctrans.c
        distrib/jpeg-6b/jdapimin.c
        distrib/jpeg-6b/jdapistd.c
        distrib/jpeg-6b/jdatadst.c
        distrib/jpeg-6b/jdatasrc.c
        distrib/jpeg-6b/jdcoefct.c
        distrib/jpeg-6b/jdcolor.c
        distrib/jpeg-6b/jddctmgr.c
        distrib/jpeg-6b/jdhuff.c
        distrib/jpeg-6b/jdinput.c
        distrib/jpeg-6b/jdmainct.c
        distrib/jpeg-6b/jdmarker.c
        distrib/jpeg-6b/jdmaster.c
        distrib/jpeg-6b/jdmerge.c
        distrib/jpeg-6b/jdphuff.c
        distrib/jpeg-6b/jdpostct.c
        distrib/jpeg-6b/jdsample.c
        distrib/jpeg-6b/jdtrans.c
        distrib/jpeg-6b/jerror.c
        distrib/jpeg-6b/jfdctflt.c
        distrib/jpeg-6b/jfdctfst.c
        distrib/jpeg-6b/jfdctint.c
        distrib/jpeg-6b/jidctflt.c
        distrib/jpeg-6b/jidctfst.c
        distrib/jpeg-6b/jidctint.c
        distrib/jpeg-6b/jidctred.c
        distrib/jpeg-6b/jquant1.c
        distrib/jpeg-6b/jquant2.c
        distrib/jpeg-6b/jutils.c
        distrib/jpeg-6b/jmemmgr.c
        distrib/jpeg-6b/jmem-android.c
        distrib/jpeg-6b/jidctintelsse.c

# PNG
        distrib/libpng-1.2.46/png.c
        distrib/libpng-1.2.46/pngerror.c
        distrib/libpng-1.2.46/pngget.c
        distrib/libpng-1.2.46/pngmem.c
        distrib/libpng-1.2.46/pngpread.c
        distrib/libpng-1.2.46/pngread.c
        distrib/libpng-1.2.46/pngrio.c
        distrib/libpng-1.2.46/pngrtran.c
        distrib/libpng-1.2.46/pngrutil.c
        distrib/libpng-1.2.46/pngset.c
        distrib/libpng-1.2.46/pngtrans.c
        distrib/libpng-1.2.46/pngvcrd.c
        distrib/libpng-1.2.46/pngwio.c
        distrib/libpng-1.2.46/pngwrite.c
        distrib/libpng-1.2.46/pngwtran.c
        distrib/libpng-1.2.46/pngwutil.c
        distrib/libpng-1.2.46/pnggccrd.c

# EXT4  distrib/ext4_utils
        distrib/ext4_utils/src/allocate.c
        distrib/ext4_utils/src/contents.c
        distrib/ext4_utils/src/crc16.c
        distrib/ext4_utils/src/ext4_sb.c
        distrib/ext4_utils/src/ext4_utils.c
        distrib/ext4_utils/src/extent.c
        distrib/ext4_utils/src/indirect.c
        distrib/ext4_utils/src/make_ext4fs.c
        distrib/ext4_utils/src/sha1.c
        distrib/ext4_utils/src/uuid.c
        distrib/ext4_utils/src/wipe.c

# GLIB  dtrib/mini-glib
        distrib/mini-glib/src/glib-mini.c

        android/wear-agent/android_wear_agent.cpp
        android/wear-agent/WearAgent.cpp
        android/wear-agent/PairUpWearPhone.cpp

        android/audio-test.c
)

target_compile_definitions(emulator PUBLIC
    -DUSE_MMX=1
    -D_XOPEN_SOURCE=600 -D_BSD_SOURCE=1

    -DANDROID_BUILD_ID=build_id
    -DANDROID_SDK_TOOLS_REVISION=tools_revision
    -D_FILE_OFFSET_BITS=64
    -D_LARGEFILE_SOURCE
    -DNEED_CPU_H
    -DNEED_TYPEDEFS # libslurp

    -DTARGET_ARCH=\"x86\"
    -DCONFIG_BDRV_WHITELIST=\"\"

    -DHAS_AUDIO

    -DAVOID_TABLES
    -DANDROID_TILE_BASED_DECODE
    -DANDROID_INTELSSE2_IDCT
    -DHOST    
    -DSDL_VIDEO_OPENGL_EGL=1
)

target_include_directories(emulator PUBLIC
    .
    include
    android/config/target-x86
    distrib/mini-glib/include
    distrib/ext4_utils/include
    distrib/libsparse/include
    qapi-auto-generated
    target-i386
    telephony
    slirp-android
    distrib/sdl2-2.0.3/include
    distrib/sdl2-2.0.3/config/include
    distrib/sdl2-2.0.3/config/include/dynapi
    proxy
    distrib/jpeg-6b
    tcg
    tcg/i386
    distrib/libpng-1.2.46

    distrib/android-emugl/host/libs/Translator/include
    android/wear-agent/include
)
if(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
    target_sources(emulator PRIVATE
        os-win32.c
        util/oslib-win32.c
        android/base/synchronization/ConditionVariable_win32.cpp
        android/base/threads/Thread_win32.cpp
        target-i386/hax-windows.c
        audio/winaudio.c
        tap-win32.c
        android/camera/camera-capture-windows.c
        util/qemu-thread-win32.c

# SDL2  distrib/sdl2-2.0.3/src
        distrib/sdl2-2.0.3/src/core/windows/SDL_windows.c
        distrib/sdl2-2.0.3/src/loadso/windows/SDL_sysloadso.c
        distrib/sdl2-2.0.3/src/thread/generic/SDL_syscond.c
        distrib/sdl2-2.0.3/src/thread/windows/SDL_sysmutex.c
        distrib/sdl2-2.0.3/src/thread/windows/SDL_syssem.c
        distrib/sdl2-2.0.3/src/thread/windows/SDL_systhread.c
        distrib/sdl2-2.0.3/src/thread/windows/SDL_systls.c
        distrib/sdl2-2.0.3/src/timer/windows/SDL_systimer.c
#        distrib/sdl2-2.0.3/src/audio/xaudio2/SDL_xaudio2.c
        distrib/sdl2-2.0.3/src/audio/directsound/SDL_directsound.c
        distrib/sdl2-2.0.3/src/audio/winmm/SDL_winmm.c
# src/video
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsclipboard.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsevents.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsframebuffer.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowskeyboard.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsmessagebox.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsmodes.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsmouse.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsopengl.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsshape.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsvideo.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowswindow.c
        distrib/sdl2-2.0.3/src/video/windows/SDL_windowsopengles.c
# src/joystick
        distrib/sdl2-2.0.3/src/joystick/windows/SDL_dxjoystick.c
        distrib/sdl2-2.0.3/src/joystick/windows/SDL_mmjoystick.c
# src/haptic
        distrib/sdl2-2.0.3/src/haptic/windows/SDL_syshaptic.c
# src/main
        distrib/sdl2-2.0.3/src/main/windows/SDL_windows_main.c

# GLIB
        distrib/mini-glib/src/glib-mini-win32.c
    )
    target_compile_definitions(emulator PRIVATE
        -DUSE_MINGW=1
#        -falign-functions=0
        -D_GNU_SOURCE=1 -Dmain=SDL_main -DNO_STDIO_REDIRECT=1
        -DSDL_VIDEO_OPENGL_EGL=0 -DSDL_VIDEO_RENDER_OGL_ES2=0
        -DSDL_AUDIO_DISABLED=1
        -D_WIN32
        -D_WIN64
        -DWINVER=0x501

        -DCONFIG_WINAUDIO
        -D__USE_MINGW_ANSI_STDIO=1
    )
    target_link_libraries(emulator
        ws2_32 winmm iphlpapi vfw32 imm32 version
    )
    target_compile_options(emulator PRIVATE
        -Wl,--allow-undefined
    )
    target_include_directories(emulator PRIVATE
        android/config/windows
    )
else()
    target_sources(emulator PRIVATE
        android/base/threads/Thread_pthread.cpp
        distrib/sdl2-2.0.3/src/timer/unix/SDL_systimer.c
        distrib/sdl2-2.0.3/src/loadso/dlopen/SDL_sysloadso.c
        distrib/sdl2-2.0.3/src/main/dummy/SDL_dummy_main.c
        distrib/sdl2-2.0.3/src/thread/pthread/SDL_syscond.c
        distrib/sdl2-2.0.3/src/thread/pthread/SDL_sysmutex.c
        distrib/sdl2-2.0.3/src/thread/pthread/SDL_syssem.c
        distrib/sdl2-2.0.3/src/thread/pthread/SDL_systhread.c
        distrib/sdl2-2.0.3/src/thread/pthread/SDL_systls.c

        os-posix.c
        util/oslib-posix.c

        distrib/libselinux/src/callbacks.c
        distrib/libselinux/src/check_context.c
        distrib/libselinux/src/freecon.c
        distrib/libselinux/src/init.c
        distrib/libselinux/src/label.c
        distrib/libselinux/src/label_file.c
        distrib/libselinux/src/label_android_property.c

    )
    target_include_directories(emulator PRIVATE
        distrib/libselinux/include
    )
    # TODO: add libselinux sources.
endif()

if(${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    find_library(COCOA_LIBRARY Cocoa)
    find_library(COREFOUNDATION_LIBRARY CoreFoundation )
    find_library(APPSVC_LIBRARY ApplicationServices)
    find_library(OPENGL_LIBRARY OpenGL)
    find_library(CARBON_LIBRARY Carbon)
    find_library(IOKIT_LIBRARY IOKit)
    find_library(COREADUIO_LIBRARY CoreAudio)
    find_library(COREVIDEO_LIBRARY CoreVideo)
    find_library(QTKIT_LIBRARY QtKit)
    find_library(AVF_LIBRARY AVFoundation)
    find_library(CM_LIBRARY CoreMedia)
    find_library(AU_LIBRARY AudioUnit)
    find_library(FF_LIBRARY ForceFeedback)
    target_compile_definitions(emulator PRIVATE
        -D_DARWIN_C_SOURCE=1
        -D_GNU_SOURCE=1
        -DTHREAD_SAFE
        -DDARWIN
        -DCONFIG_COREAUDIO
        -DHOST_BSD=1
    )
    target_include_directories(emulator PRIVATE
        android/config/darwin-x86_64
    )
    target_link_libraries(emulator PRIVATE
        ${COREFOUNDATION_LIBRARY} ${APPSVC_LIBRARY} ${OPENGL_LIBRARY}
        ${CARBON_LIBRARY} ${IOKIT_LIBRARY} ${COCOA_LIBRARY} ${AVF_LIBRARY}
        ${COREVIDEO_LIBRARY} ${COREADUIO_LIBRARY} ${QTKIT_LIBRARY}
        ${CM_LIBRARY} ${AU_LIBRARY} ${FF_LIBRARY}
        /usr/lib/dylib1.o
    )
    target_sources(emulator PRIVATE
        distrib/sdl2-2.0.3/src/haptic/darwin/SDL_syshaptic.c
        distrib/sdl2-2.0.3/src/audio/coreaudio/SDL_coreaudio.c
        distrib/sdl2-2.0.3/src/file/cocoa/SDL_rwopsbundlesupport.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoaclipboard.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoaevents.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoakeyboard.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoamessagebox.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoamodes.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoamouse.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoamousetap.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoaopengl.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoashape.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoavideo.m
        distrib/sdl2-2.0.3/src/video/cocoa/SDL_cocoawindow.m
        distrib/sdl2-2.0.3/src/joystick/darwin/SDL_sysjoystick.c

        audio/coreaudio.c

        android/camera/camera-capture-mac.m
        util/compatfd.c
        util/qemu-thread-posix.c
        target-i386/hax-darwin.c

    )
endif()

# AUTOGENERATED_DIR=qapi-auto-generated
# python android/tools/gen-hw-config.py android/avd/hardware-properties.ini android/avd/hw-config-defs.h
# python scripts/qapi-types.py qapi.types --output-dir=$AUTOGENERATED_DIR -b < qapi-schema.json
# python scripts/qapi-visit.py --output-dir=$AUTOGENERATED_DIR -b < qapi-schema.json
# python scripts/qapi-commands.py --output-dir=$AUTOGENERATED_DIR -m < qapi-schema.json
# hxtool -h < qemu-options.hx > qemu-options.h
# hxtool -h < qemu-options.hx > qemu-options.def
