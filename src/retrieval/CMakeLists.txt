add_library( retriever retriever.cpp )
target_link_libraries( retriever )

add_library( spatial_retriever spatial_retriever.cpp )
target_link_libraries( spatial_retriever same_random )

add_library( multi_query multi_query.cpp )
target_link_libraries( multi_query retriever ${Boost_LIBRARIES})

add_library( nn_raw_single_retriever nn_raw_single_retriever.cpp )
target_link_libraries( nn_raw_single_retriever retriever coarse_residual )

add_library( nn_single_retriever nn_single_retriever.cpp )
target_link_libraries( nn_single_retriever retriever coarse_residual ${Boost_LIBRARIES} )
