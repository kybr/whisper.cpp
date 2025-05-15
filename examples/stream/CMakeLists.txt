if (WHISPER_SDL2)
    set(TARGET whisper-stream)
    add_executable(${TARGET} stream.cpp)

    include(DefaultTargetOptions)

    target_include_directories(${TARGET} PUBLIC /opt/homebrew/include )
    target_link_directories(${TARGET} PUBLIC /opt/homebrew/lib )

    target_link_libraries(${TARGET} PRIVATE common common-sdl lo whisper ${CMAKE_THREAD_LIBS_INIT})

    install(TARGETS ${TARGET} RUNTIME)
endif ()
