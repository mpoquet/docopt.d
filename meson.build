project('docopt', 'd', version: '0.6.1-b.6')

src = [
    'source/argvalue.d',
    'source/docopt.d',
    'source/patterns.d',
    'source/tokens.d',
    'source/unittests.d'
]

# Explictly link standard library if ldc is used
if meson.get_compiler('d').get_id() == 'llvm'
  extra_args = ['-link-defaultlib-shared']
else
  extra_args = []
endif

incdir = include_directories('source')

lib = library('docopt',
    src,
    include_directories: [incdir],
    install: true, install_dir: 'lib',
    link_args: extra_args
)

pkgc = import('pkgconfig')
pkgc.generate(name: 'docopt-d',
    libraries: lib,
    subdirs: 'd/docopt/source',
    version: meson.project_version(),
    description: 'docopt implementation in D'
)
install_subdir('source/', install_dir: 'include/d/docopt/')
