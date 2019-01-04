project('xtensor', 'cpp',
        version:'0.19.1',
        license:'BSD-3-Clause',
        default_options : ['warning_level=3', 'cpp_std=c++14'])

xtensor_dependencies = [dependency('xtl',
                                   version:'>=0.5.1',
                                   fallback : ['xtl', 'xtl_dep'] ),
                        dependency('nlohmann_json',
                                   version:'>=3.1.1',
                                   fallback : ['nlohmann_json', 'nlohmann_json_dep'] )
                                   ]
xtensor_cpp_arg = []

if get_option('XTENSOR_USE_XSIMD')
  xtensor_dependencies+=[dependency('xsimd', version:'>=7.0.0'), fallback : ['xsimd', 'xsimd_dep']]
  xtensor_cpp_arg = ['-DXTENSOR_USE_XSIMD']
endif

xtensor_dep = declare_dependency(include_directories:include_directories('include'),
                                 dependencies:xtensor_dependencies,
                                 compile_args:xtensor_cpp_arg)

install_headers([
 'include/xtensor/xassign.hpp',
 'include/xtensor/xoptional.hpp',
 'include/xtensor/xview_utils.hpp',
 'include/xtensor/xmime.hpp',
 'include/xtensor/xnorm.hpp',
 'include/xtensor/xutils.hpp',
 'include/xtensor/xmasked_value.hpp',
 'include/xtensor/xconcepts.hpp',
 'include/xtensor/xnoalias.hpp',
 'include/xtensor/xtensor_simd.hpp',
 'include/xtensor/xhistogram.hpp',
 'include/xtensor/xarray.hpp',
 'include/xtensor/xmanipulation.hpp',
 'include/xtensor/xsort.hpp',
 'include/xtensor/xslice.hpp',
 'include/xtensor/xoptional_assembly_base.hpp',
 'include/xtensor/xreducer.hpp',
 'include/xtensor/xgenerator.hpp',
 'include/xtensor/xview.hpp',
 'include/xtensor/xmath.hpp',
 'include/xtensor/xiterator.hpp',
 'include/xtensor/xcsv.hpp',
 'include/xtensor/xoptional_assembly_storage.hpp',
 'include/xtensor/xoptional_assembly.hpp',
 'include/xtensor/xfixed.hpp',
 'include/xtensor/xdynamic_view.hpp',
 'include/xtensor/xtensor.hpp',
 'include/xtensor/xtensor_config.hpp',
 'include/xtensor/xindex_view.hpp',
 'include/xtensor/xstorage.hpp',
 'include/xtensor/xbroadcast.hpp',
 'include/xtensor/xnpy.hpp',
 'include/xtensor/xcontainer.hpp',
 'include/xtensor/xjson.hpp',
 'include/xtensor/xmasked_view.hpp',
 'include/xtensor/xio.hpp',
 'include/xtensor/xvectorize.hpp',
 'include/xtensor/xexpression_holder.hpp',
 'include/xtensor/xexpression.hpp',
 'include/xtensor/xscalar.hpp',
 'include/xtensor/xfunctor_view.hpp',
 'include/xtensor/xstrided_view.hpp',
 'include/xtensor/xbuffer_adaptor.hpp',
 'include/xtensor/xeval.hpp',
 'include/xtensor/xfunction.hpp',
 'include/xtensor/xlayout.hpp',
 'include/xtensor/xbuilder.hpp',
 'include/xtensor/xoperation.hpp',
 'include/xtensor/xtensor_forward.hpp',
 'include/xtensor/xexception.hpp',
 'include/xtensor/xadapt.hpp',
 'include/xtensor/xaccumulator.hpp',
 'include/xtensor/xoffset_view.hpp',
 'include/xtensor/xcomplex.hpp',
 'include/xtensor/xrandom.hpp',
 'include/xtensor/xiterable.hpp',
 'include/xtensor/xstrides.hpp',
 'include/xtensor/xshape.hpp',
 'include/xtensor/xsemantic.hpp',
 'include/xtensor/xinfo.hpp',
 'include/xtensor/xaxis_iterator.hpp',
 'include/xtensor/xstrided_view_base.hpp'
 ]
,
 subdir:'xtensor'
)

pkgc = import('pkgconfig')
pkgc.generate(name: 'xtensor',
    version: meson.project_version(),
    description: 'C++ tensors with broadcasting and lazy computing'
)

tests_sources = [
 'test/main.cpp',
 'test/test_extended_broadcast_view.cpp',
 'test/test_extended_xhistogram.cpp',
 'test/test_extended_xmath_interp.cpp',
 'test/test_extended_xmath_reducers.cpp',
 'test/test_xaccumulator.cpp',
 'test/test_xadapt.cpp',
 'test/test_xadaptor_semantic.cpp',
 'test/test_xarray.cpp',
 'test/test_xarray_adaptor.cpp',
 'test/test_xaxis_iterator.cpp',
 'test/test_xbroadcast.cpp',
 'test/test_xbuffer_adaptor.cpp',
 'test/test_xbuilder.cpp',
 'test/test_xcomplex.cpp',
 'test/test_xconcepts.cpp',
 'test/test_xcontainer_semantic.cpp',
 'test/test_xcsv.cpp',
 'test/test_xdatesupport.cpp',
 'test/test_xdynamic_view.cpp',
 'test/test_xeval.cpp',
 'test/test_xexception.cpp',
 'test/test_xexpression.cpp',
 'test/test_xexpression_holder.cpp',
 'test/test_xfixed.cpp',
 'test/test_xfunction.cpp',
 'test/test_xfunctor_adaptor.cpp',
 'test/test_xhistogram.cpp',
 'test/test_xindex_view.cpp',
 'test/test_xinfo.cpp',
 'test/test_xio.cpp',
 'test/test_xiterator.cpp',
 'test/test_xjson.cpp',
 'test/test_xlayout.cpp',
 'test/test_xmanipulation.cpp',
 'test/test_xmasked_value.cpp',
 'test/test_xmasked_view.cpp',
 'test/test_xmath.cpp',
 'test/test_xmath_result_type.cpp',
 'test/test_xnan_functions.cpp',
 'test/test_xnoalias.cpp',
 'test/test_xnorm.cpp',
 'test/test_xnpy.cpp',
 'test/test_xoperation.cpp',
 'test/test_xoptional.cpp',
 'test/test_xoptional_assembly.cpp',
 'test/test_xoptional_assembly_adaptor.cpp',
 'test/test_xoptional_assembly_storage.cpp',
 'test/test_xrandom.cpp',
 'test/test_xreducer.cpp',
 'test/test_xscalar.cpp',
 'test/test_xscalar_semantic.cpp',
 'test/test_xshape.cpp',
 'test/test_xsort.cpp',
 'test/test_xstorage.cpp',
 'test/test_xstrided_view.cpp',
 'test/test_xstrides.cpp',
 'test/test_xtensor.cpp',
 'test/test_xtensor_adaptor.cpp',
 'test/test_xtensor_semantic.cpp',
 'test/test_xutils.cpp',
 'test/test_xvectorize.cpp',
 'test/test_xview.cpp',
 'test/test_xview_semantic.cpp'
 ]

benchmark_sources = [
 'benchmark/benchmark_adapter.cpp',
 'benchmark/benchmark_assign.cpp',
 'benchmark/benchmark_builder.cpp',
 'benchmark/benchmark_container.cpp',
 'benchmark/benchmark_creation.cpp',
 'benchmark/benchmark_increment_stepper.cpp',
 'benchmark/benchmark_lambda_expressions.cpp',
 'benchmark/benchmark_math.cpp',
 'benchmark/benchmark_random.cpp',
 'benchmark/benchmark_reducer.cpp',
 'benchmark/benchmark_views.cpp',
 'benchmark/benchmark_view_access.cpp',
 'benchmark/benchmark_view_adapt.cpp',
 'benchmark/benchmark_view_assignment.cpp',
 'benchmark/benchmark_xshape.cpp',
 'benchmark/main.cpp'
 ]


if get_option('BUILD_TESTS')
  cpp_args = []
  gtest_dep = dependency('gtest', main : true, fallback : ['gtest', 'gtest_dep'])
  test_exe = executable('xtensor-test', tests_sources,
                        dependencies:[xtensor_dep, gtest_dep],
                        cpp_args:cpp_args)
  test('xtensor-test', test_exe, workdir : meson.current_source_dir()+'/test')

  benchmark_dep = dependency('benchmark', fallback : ['google-benchmark', 'google_benchmark_dep'])
  benchmark_exe = executable('xsimd-benchmark', benchmark_sources,
                             dependencies : [xtensor_dep, benchmark_dep],
                             cpp_args:cpp_args)
  benchmark('xsimd-benchmark', benchmark_exe, timeout:3600)
endif
