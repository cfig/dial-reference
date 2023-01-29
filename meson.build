project('dial server', 'c', 'cpp', default_options : ['cpp_std=c++17'])

#--------------------------------------------------
#
#--------------------------------------------------

server_sources = [
    'server/dial_data.c',
    'server/dial_server.c',
    'server/main.c',
    'server/mongoose.c',
    'server/nf_callbacks.c',
    'server/quick_ssdp.c',
    'server/system_callbacks.c',
    'server/url_lib.c',
  ]

executable(
    'dialserver', 
    server_sources,
    cpp_args: '-DDEBUG',
    link_args : '-pthread',
  )

client_sources = [
    'client/DialClientInput.cpp',
    'client/DialConformance.cpp',
    'client/DialDiscovery.cpp',
    'client/DialServer.cpp',
    'client/main.cpp',
  ]

thread_dep = dependency('threads')
curl_dep = dependency('libcurl')
crypto_dep = dependency('libcrypto')
ssl_dep = dependency('libssl')

executable(
    'dialclient', 
    client_sources,
    cpp_args: '-DDEBUG',
    link_args: '-lz',
    dependencies : [thread_dep, curl_dep, crypto_dep, ssl_dep ]
  )
