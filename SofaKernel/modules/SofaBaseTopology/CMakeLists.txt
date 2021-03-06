cmake_minimum_required(VERSION 3.1)
project(SofaBaseTopology)


set(HEADER_FILES
    CommonAlgorithms.h
    EdgeSetGeometryAlgorithms.h
    EdgeSetGeometryAlgorithms.inl
    EdgeSetTopologyAlgorithms.h
    EdgeSetTopologyAlgorithms.inl
    EdgeSetTopologyContainer.h
    EdgeSetTopologyModifier.h
    GridTopology.h
    HexahedronSetGeometryAlgorithms.h
    HexahedronSetGeometryAlgorithms.inl
    HexahedronSetTopologyAlgorithms.h
    HexahedronSetTopologyAlgorithms.inl
    HexahedronSetTopologyContainer.h
    HexahedronSetTopologyModifier.h
    MeshTopology.h
    NumericalIntegrationDescriptor.h
    NumericalIntegrationDescriptor.inl
    PointSetGeometryAlgorithms.h
    PointSetGeometryAlgorithms.inl
    PointSetTopologyAlgorithms.h
    PointSetTopologyAlgorithms.inl
    PointSetTopologyContainer.h
    PointSetTopologyModifier.h
    QuadSetGeometryAlgorithms.h
    QuadSetGeometryAlgorithms.inl
    QuadSetTopologyAlgorithms.h
    QuadSetTopologyAlgorithms.inl
    QuadSetTopologyContainer.h
    QuadSetTopologyModifier.h
    RegularGridTopology.h
    SparseGridTopology.h
    TetrahedronSetGeometryAlgorithms.h
    TetrahedronSetGeometryAlgorithms.inl
    TetrahedronSetTopologyAlgorithms.h
    TetrahedronSetTopologyAlgorithms.inl
    TetrahedronSetTopologyContainer.h
    TetrahedronSetTopologyModifier.h
    TopologyData.h
    TopologyData.inl
    TopologyDataHandler.h
    TopologyDataHandler.inl
    TopologyEngine.h
    TopologyEngine.inl
    TopologySparseData.h
    TopologySparseData.inl
    TopologySparseDataHandler.h
    TopologySparseDataHandler.inl
    TopologySubsetData.h
    TopologySubsetData.inl
    TopologySubsetDataHandler.h
    TopologySubsetDataHandler.inl
    TriangleSetGeometryAlgorithms.h
    TriangleSetGeometryAlgorithms.inl
    TriangleSetTopologyAlgorithms.h
    TriangleSetTopologyAlgorithms.inl
    TriangleSetTopologyContainer.h
    TriangleSetTopologyModifier.h
    config.h
    initBaseTopology.h
)

set(SOURCE_FILES
    EdgeSetGeometryAlgorithms.cpp
    EdgeSetTopologyAlgorithms.cpp
    EdgeSetTopologyContainer.cpp
    EdgeSetTopologyModifier.cpp
    GridTopology.cpp
    HexahedronSetGeometryAlgorithms.cpp
    HexahedronSetTopologyAlgorithms.cpp
    HexahedronSetTopologyContainer.cpp
    HexahedronSetTopologyModifier.cpp
    MeshTopology.cpp
    NumericalIntegrationDescriptor.cpp
    PointSetGeometryAlgorithms.cpp
    PointSetTopologyAlgorithms.cpp
    PointSetTopologyContainer.cpp
    PointSetTopologyModifier.cpp
    QuadSetGeometryAlgorithms.cpp
    QuadSetTopologyAlgorithms.cpp
    QuadSetTopologyContainer.cpp
    QuadSetTopologyModifier.cpp
    RegularGridTopology.cpp
    SparseGridTopology.cpp
    TetrahedronSetGeometryAlgorithms.cpp
    TetrahedronSetTopologyAlgorithms.cpp
    TetrahedronSetTopologyContainer.cpp
    TetrahedronSetTopologyModifier.cpp
    TriangleSetGeometryAlgorithms.cpp
    TriangleSetTopologyAlgorithms.cpp
    TriangleSetTopologyContainer.cpp
    TriangleSetTopologyModifier.cpp
    initBaseTopology.cpp
)

add_library(${PROJECT_NAME} SHARED ${HEADER_FILES} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} PUBLIC SofaSimulationCommon)
set_target_properties(${PROJECT_NAME} PROPERTIES COMPILE_FLAGS "-DSOFA_BUILD_BASE_TOPOLOGY")
set_target_properties(${PROJECT_NAME} PROPERTIES PUBLIC_HEADER "${HEADER_FILES}")

sofa_install_targets(SofaBase ${PROJECT_NAME} "SofaBase/${PROJECT_NAME}")
