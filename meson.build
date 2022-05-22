project('cxxshim', default_options: ['cpp_std=c++20'])

incl = include_directories('stage2/include')

cxxshim_dep = declare_dependency(include_directories: incl)

clang_coroutine_dep = declare_dependency(
	include_directories: include_directories('clang-coroutine/include')
)

std_coroutine_dep = declare_dependency(
	include_directories: include_directories('std-coroutine/include')
)

if get_option('install_headers')
	install_headers(
		'stage2/include/algorithm',
		'stage2/include/atomic',
		'stage2/include/cstddef',
		'stage2/include/cstdint',
		'stage2/include/initializer_list',
		'stage2/include/iterator',
		'stage2/include/memory',
		'stage2/include/new',
		'stage2/include/tuple',
		'stage2/include/type_traits',
		'stage2/include/utility',
		subdir: 'stage2',
	)
	install_headers(
		'clang-coroutine/include/experimental/coroutine',
		subdir: 'clang-coroutine/experimental',
	)
	install_headers(
		'std-coroutine/include/coroutine',
		subdir: 'std-coroutine',
	)
endif

pkg = import('pkgconfig')
pkg.generate(
	name: 'cxxshim',
	description: 'Shim for freestanding C++',
	subdirs: ['stage2'],
)
pkg.generate(
	name: 'cxxshim-coroutine-clang',
	description: 'Shim for freestanding C++ (clang coroutine headers)',
	subdirs: ['clang-coroutine'],
)
pkg.generate(
	name: 'cxxshim-coroutine-std',
	description: 'Shim for freestanding C++ (std coroutine headers)',
	subdirs: ['std-coroutine'],
)
