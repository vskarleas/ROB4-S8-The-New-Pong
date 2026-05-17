# Our executables
add_executable(user_test user_test.cpp)
add_executable(ball_test ball_test.cpp)
add_executable(paddle_test paddle_test.cpp)
add_executable(letter_test letter_test.cpp)

# Associating any libraries that are may needed for the tests.
# The parent CMakeLists.txt defines SDL2_ALL_LIBS per-platform; reuse it here.
target_link_libraries(user_test PRIVATE ${PROJECT_NAME}_lib)
target_link_libraries(ball_test
    PRIVATE
    ${PROJECT_NAME}_lib
    ${SDL2_ALL_LIBS}
)
target_link_libraries(paddle_test
    PRIVATE
    ${PROJECT_NAME}_lib
    ${SDL2_ALL_LIBS}
)
target_link_libraries(letter_test
    PRIVATE
    ${PROJECT_NAME}_lib
    ${SDL2_ALL_LIBS}
)

# CTest config
add_test(NAME User_class COMMAND user_test)
add_test(NAME Ball_classes COMMAND ball_test)
add_test(NAME Paddle_class COMMAND paddle_test)
add_test(NAME Letter_class COMMAND letter_test)