set(SRCS
    main.cpp
    ../dependencies/imgui-cmake/libs/imgui/imconfig.h
    ../dependencies/imgui-cmake/libs/imgui/imgui.cpp
    ../dependencies/imgui-cmake/libs/imgui/imgui.h
    ../dependencies/imgui-cmake/libs/imgui/imgui_demo.cpp
    ../dependencies/imgui-cmake/libs/imgui/imgui_draw.cpp
    ../dependencies/imgui-cmake/libs/imgui/imgui_internal.h
    ../dependencies/imgui-cmake/libs/imgui/imgui_widgets.cpp
    ../dependencies/imgui-cmake/libs/imgui/imstb_rectpack.h
    ../dependencies/imgui-cmake/libs/imgui/imstb_textedit.h
    ../dependencies/imgui-cmake/libs/imgui/imstb_truetype.h
    ../dependencies/imgui-cmake/libs/imgui/backends/imgui_impl_opengl3.cpp
    ../dependencies/imgui-cmake/libs/imgui/backends/imgui_impl_opengl3.h
    ../dependencies/imgui-cmake/libs/imgui/backends/imgui_impl_sdl.cpp
    ../dependencies/imgui-cmake/libs/imgui/backends/imgui_impl_sdl.h)

add_executable (3DEngine ${SRCS})
target_link_libraries(3DEngine fmt)
target_link_libraries(3DEngine IMGUI)
target_link_libraries(3DEngine glfw)
target_link_libraries(3DEngine glad)
target_link_libraries(${CMAKE_PROJECT_NAME}
"-framework Cocoa"
"-framework IOKit"
"-framework CoreVideo"
)

install(PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/3DEngine
  DESTINATION bin
  RENAME ${CMAKE_PROJECT_NAME}-3DEngine)