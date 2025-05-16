src = files(
  'src' / 'main.cpp',
  'src' / 'handlers' / 'confighandler.cpp',
  'src' / 'handlers' / 'ocsurlhandler.cpp',
)

src += qt.compile_moc(
  headers: [
    'src' / 'handlers' / 'confighandler.h',
    'src' / 'handlers' / 'ocsurlhandler.h',
  ],
  dependencies: [qt_dep, qtil_dep],
)

src += qt.compile_resources(
  sources: [
    'configs' / 'configs.qrc',
    'images' / 'images.qrc',
    'qml' / 'qml.qrc',
  ],
)

# TODO: does QMLs need compile?
