SET(PACKAGE_SQL_FILES "")
SET(L_PACKAGE_SQL_FILES "")

ADD_SUBDIRECTORY(common)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(astar)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(bd_astar)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(dijkstra)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(kdijkstra)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(bd_dijkstra)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(apsp_johnson)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(apsp_warshall)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

#ADD_SUBDIRECTORY(shooting_star)
#LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(trsp)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

ADD_SUBDIRECTORY(tsp)
LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")

if("${POSTGRESQL_VERSION}" VERSION_GREATER "8.4.0")
    ADD_SUBDIRECTORY(ksp)
    LIST(APPEND L_PACKAGE_SQL_FILES "${PACKAGE_SQL_FILES}")
endif("${POSTGRESQL_VERSION}" VERSION_GREATER "8.4.0")


# Make sure this is after all the ADD_SUBDIRECTORY
SET(PACKAGE_SQL_FILES "${L_PACKAGE_SQL_FILES}" PARENT_SCOPE)
