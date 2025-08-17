project('cstl', 'c', default_options: ['c_std=c99'])

catch2_dep = dependency('catch2', method: 'pkg-config', required: not get_option('BUILD_TEST'))

cstl_lib = include_directories('src/')
test_src = files() # empty because no tests created yet

if get_option('BUILD_TEST')
  build_test = executable('cstl_build_test', 'tests/build.c', include_directories: cstl_lib)
  test('c99 header build test', build_test)
else
  test_bin = executable('cstl_test', test_src, include_directories: cstl_lib, cpp_args: 'std=c++14', dependencies: catch2_dep)
  test('catch2 unit tests', test_bin, is_parallel: false)
endif
