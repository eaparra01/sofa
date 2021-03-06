cmake_minimum_required(VERSION 3.1)
project(SofaMiscFem_test)

set(HEADER_FILES
    )
set(SOURCE_FILES
    # Unit test TODO (htalbot): improve the parameters and initialization
    TetrahedronHyperelasticityFEMForceField_params_test.cpp
    # Test of regression for hyperelasticity (MooneyRivlin)
    TetrahedronHyperelasticityFEMForceField_scene_test.cpp
    )

if(SOFA_WITH_DEPRECATED_COMPONENTS)
    list(APPEND HEADER_FILES
        LennardJonesForceField_test.h
        LennardJonesForceField_test.inl
        )
    list(APPEND SOURCE_FILES
        LennardJonesForceField_test.cpp
        )
endif()

add_executable(${PROJECT_NAME} ${SOURCE_FILES})
add_definitions("-DSOFAMISCFEM_TEST_SCENES_DIR=\"${CMAKE_CURRENT_SOURCE_DIR}/scenes\"")
target_link_libraries(${PROJECT_NAME} SofaGTestMain SofaTest)
add_test(NAME ${PROJECT_NAME} COMMAND ${PROJECT_NAME})
