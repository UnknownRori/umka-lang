project('umka', 'c')
src = files(
  'src/umka_api.c',
  'src/umka_common.c',
  'src/umka_compiler.c',
  'src/umka_const.c',
  'src/umka_decl.c',
  'src/umka_expr.c',
  'src/umka_gen.c',
  'src/umka_ident.c',
  'src/umka_lexer.c',
  'src/umka_runtime.c',
  'src/umka_stmt.c',
  'src/umka_types.c',
  'src/umka_vm.c',
)

inc = include_directories('./src')

c_args = ['-DUMKA_BUILD']

if get_option('BUILD_STATIC')
  c_args += '-DUMKA_STATIC'
endif

umka_lib = library(
  meson.project_name(), 
  src, 
  include_directories: [inc],
  c_args: c_args,
)

umka_dep = declare_dependency(
  link_with: umka_lib,
  include_directories: [inc],
  compile_args: c_args,
)
