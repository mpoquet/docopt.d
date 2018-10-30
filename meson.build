project('docopt', 'd', version: '0.6.1-b.6')

src = [
    'source/argvalue.d',
    'source/docopt.d',
    'source/patterns.d',
    'source/tokens.d',
    'source/unittests.d'
]

incdir = include_directories('source')

lib = library('docopt',
    src,
    include_directories: [incdir],
    install: true, install_dir: 'lib'
)

pkgc = import('pkgconfig')
pkgc.generate(name: 'docopt-d',
    libraries: lib,
    subdirs: 'd/docopt/source',
    version: meson.project_version(),
    description: 'docopt implementation in D'
)
install_subdir('source/', install_dir: 'include/d/docopt/')
