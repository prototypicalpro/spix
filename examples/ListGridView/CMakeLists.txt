set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SPIX_QT_MAJOR "6" CACHE STRING "Major Qt version to build Spix against")

find_package(Qt${SPIX_QT_MAJOR} COMPONENTS Core Quick REQUIRED)

add_executable(SpixListGridViewExample "main.cpp" "qml.qrc")
target_compile_definitions(SpixListGridViewExample PRIVATE $<$<OR:$<CONFIG:Debug>,$<CONFIG:RelWithDebInfo>>:QT_QML_DEBUG>)
target_link_libraries(SpixListGridViewExample PRIVATE Qt${SPIX_QT_MAJOR}::Core Qt${SPIX_QT_MAJOR}::Quick Spix)
