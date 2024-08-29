project(
  'meson_demo',
  'cpp',
  version: '0.1',
  default_options: ['warning_level=2']
)

dpdk_opt = [
    'enable_drivers=net/af_packet',
    'tests=false',
    'examples=',
    'disable_apps=test-cmdline,test-flow-perf,test-pmd',
    'enable_libs=log,eal,mempool,mbuf',
    'enable_kmods=false',
    'enable_driver_sdk=true',
    'max_numa_nodes=1'
  ]
dpdk_dep = subproject('dpdk', default_options: dpdk_opt).get_variable('dpdk_dep').as_system('system')

subdir('src')