set(WAYWARD_HEADERS
    app.hpp
    def.hpp
    http.hpp
    server.hpp
    util/linklist.hpp
)

set(WAYWARD_SOURCES
    wayward.cpp
    app.cpp
    server.cpp
)

add_library(wayward SHARED ${WAYWARD_SOURCES} ${WAYWARD_HEADERS})
add_dependencies(wayward http_parser)
target_include_directories(wayward PRIVATE ${HTTPPARSER_INCLUDE_DIR})
target_link_libraries(wayward Threads::Threads)
target_link_libraries(wayward ${HTTPPARSER_LIBS})
