libalsa_util_sources = [
  'alsa-util.c',
  'alsa-ucm.c',
  'alsa-mixer.c',
  'alsa-sink.c',
  'alsa-source.c',
  '../reserve-wrap.c',
]

libalsa_util_headers = [
  'alsa-util.h',
  'alsa-ucm.h',
  'alsa-mixer.h',
  'alsa-sink.h',
  'alsa-source.h',
  '../reserve-wrap.h',
]

if dbus_dep.found()
    libalsa_util_sources += [ '../reserve.c', '../reserve-monitor.c' ]
    libalsa_util_headers += [ '../reserve.h', '../reserve-monitor.h' ]
endif

libalsa_util = static_library('libalsa_util',
  libalsa_util_sources,
  libalsa_util_headers,
  c_args : [pa_c_args, server_c_args],
  include_directories : [configinc, topinc],
  dependencies : [libpulse_dep, libpulsecore_dep, alsa_dep, dbus_dep],
  install : false
)
