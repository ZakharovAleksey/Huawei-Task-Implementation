cmake_minimum_required(VERSION 3.5)

set(
	source_list
	"Task_5/bin_tree/bin_tree.h"
	"Task_5/bin_tree/bin_tree_impl.h"
	"Task_5/test/test.h"
	"Task_5/test/test.cpp"
	"Task_6/generator/generator.h"
	"Task_6/generator/generator.cpp"
	"Task_6/graph/graph.h"
	"Task_6/graph/graph.cpp"
	"Manager/manager.h"
	"Manager/manager.cpp"
	"main.cpp"
)

add_executable(${PROJECT_NAME} ${source_list})

foreach(source IN LISTS source_list)
    get_filename_component(source_path "${source}" PATH)
    string(REPLACE "/" "\\" source_path_msvc "${source_path}")
    source_group("${source_path_msvc}" FILES "${source}")
endforeach()
