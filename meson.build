project('hypersonik', 'c', version: '0.4.0')

add_global_arguments(
    '-Wall',
    '-DCOBJMACROS',
    '-D_WIN32_WINNT=0x0600',
    '-ffunction-sections',
    '-fdata-sections',
    language: 'c',
)

add_global_link_arguments(
    '-Wl,--gc-sections',
    '-mwindows',
    '-static-libgcc',
    language: 'c',
)

if get_option('buildtype') == 'release'
    add_global_arguments('-DNDEBUG', language: 'c')
endif

cc = meson.get_compiler('c')
lib_avrt = cc.find_library('avrt')
lib_msacm32 = cc.find_library('msacm32')

inc = include_directories(
    'guid',
    'src',
)

subdir('guid')
subdir('src')
