project('cxxshim', 'cpp')

incl = include_directories('stage2/include')

# TODO: install_headers

cxxshim_dep = declare_dependency(include_directories: incl)

clang_coroutine_dep = declare_dependency(
	include_directories: include_directories('clang-coroutine/include')
)

std_coroutine_dep = declare_dependency(
	include_directories: include_directories('std-coroutine/include')
)

