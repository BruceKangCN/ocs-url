project(
  'ocs-url',
  'cpp',
  meson_version: '>= 1.7.0',
  default_options: ['warning_level=3', 'cpp_std=c++17'],
)

add_project_arguments('-D', 'QT_DEPRECATED_WARNINGS' ,language: ['cpp'])

qt_dep = dependency(
  'Qt6',
  modules: [
    'Core',
    'Gui',
    'Widgets',
    'Qml',
    'Quick',
    'Svg',
  ],
)
qtil_dep = dependency('qtil', fallback: 'qtil')

qt = import('qt6')

subdir('app')
subdir('i18n')
subdir('desktop')

executable(
  'ocs-url',
  src,
  dependencies: [qt_dep, qtil_dep],
  install: true,
)
