project(
  'qtil',
  'cpp',
  meson_version: '>= 1.3.0',
  default_options: ['warning_level=0', 'cpp_std=c++17'],
)

cpp_args = []
if target_machine.system() in ['linux', 'openbsd', 'netbsd']
  cpp_args += ['-D', 'QTIL_OS_UNIX']
endif

inc = include_directories('src')

qt_mods = ['Core', 'Network']

if target_machine.system() == 'android'
  qt_mods += ['AndroidExtras']
endif

qt_dep = dependency('Qt6', modules: qt_mods)

src = files(
  'src' / 'qtil_config.cpp',
  'src' / 'qtil_file.cpp',
  'src' / 'qtil_dir.cpp',
  'src' / 'qtil_json.cpp',
  'src' / 'qtil_networkresource.cpp',
  'src' / 'qtil_ocsapi.cpp',
  'src' / 'qtil_package.cpp',
)

qt = import('qt6')

src += qt.compile_moc(
  headers: [
    'src' / 'qtil_config.h',
    'src' / 'qtil_file.h',
    'src' / 'qtil_dir.h',
    'src' / 'qtil_json.h',
    'src' / 'qtil_networkresource.h',
    'src' / 'qtil_ocsapi.h',
    'src' / 'qtil_package.h',
  ],
  extra_args: cpp_args,
  include_directories: inc,
  dependencies: [qt_dep],
)

lib = static_library(
  'qtil',
  src,
  cpp_args: cpp_args,
  include_directories: inc,
  dependencies: [qt_dep],
  install: true,
)

qtil_dep = declare_dependency(
  compile_args: cpp_args,
  include_directories: inc,
  link_with: lib,
)
meson.override_dependency('qtil', qtil_dep)
