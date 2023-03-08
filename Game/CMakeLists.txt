# --------------------------LIBRARY SDL --------------------------------
include(FetchContent)

FetchContent_Declare(
        SDL2
        GIT_REPOSITORY  https://github.com/libsdl-org/SDL
        GIT_TAG         release-2.0.22
        GIT_PROGRESS    TRUE
        OVERRIDE_FIND_PACKAGE TRUE
)
FetchContent_MakeAvailable(SDL2)

FetchContent_Declare(
        SDL2_IMAGE
        GIT_REPOSITORY  https://github.com/libsdl-org/SDL_image
        GIT_TAG         release-2.6.3
        GIT_PROGRESS    TRUE
        OVERRIDE_FIND_PACKAGE TRUE
)
FetchContent_MakeAvailable(SDL2_IMAGE)

# --------------------------SOURCE --------------------------------
include_directories(
        ${CMAKE_CURRENT_LIST_DIR}/public
)

file(
        GLOB_RECURSE SOURCES
        LIST_DIRECTORIES true
        CONFIGURE_DEPENDS true
        ${CMAKE_CURRENT_LIST_DIR}/private/*.cpp
)

# -------------------------- TARGETS --------------------------------
add_executable(
        ${CMAKE_PROJECT_NAME}_game
        ${SOURCES}
)

target_link_libraries(
        ${CMAKE_PROJECT_NAME}_game
        SDL2main
        SDL2-static
        SDL2_image
)