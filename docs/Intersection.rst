RhinoCompute.Intersection
=========================

.. js:module:: RhinoCompute

.. js:function:: RhinoCompute.Intersection.curvePlane(curve, plane, tolerance, multiple=false)

   Intersects a curve with an (infinite) plane.

   :param rhino3dm.Curve curve: Curve to intersect.
   :param rhino3dm.Plane plane: Plane to intersect with.
   :param float tolerance: Tolerance to use during intersection.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A list of intersection events or None if no intersections were recorded.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.meshPlane(mesh, plane, multiple=false)

   Intersects a mesh with an (infinite) plane.

   :param rhino3dm.Mesh mesh: Mesh to intersect.
   :param rhino3dm.Plane plane: Plane to intersect with.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of polylines describing the intersection loops or None (Nothing in Visual Basic) if no intersections could be found.
   :rtype: rhino3dm.Polyline[]
.. js:function:: RhinoCompute.Intersection.meshPlane1(mesh, planes, multiple=false)

   Intersects a mesh with a collection of (infinite) planes.

   :param rhino3dm.Mesh mesh: Mesh to intersect.
   :param list[rhino3dm.Plane] planes: Planes to intersect with.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of polylines describing the intersection loops or None (Nothing in Visual Basic) if no intersections could be found.
   :rtype: rhino3dm.Polyline[]
.. js:function:: RhinoCompute.Intersection.brepPlane(brep, plane, tolerance, multiple=false)

   Intersects a Brep with an (infinite) plane.

   :param rhino3dm.Brep brep: Brep to intersect.
   :param rhino3dm.Plane plane: Plane to intersect with.
   :param float tolerance: Tolerance to use for intersections.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success, False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.curveSelf(curve, tolerance, multiple=false)

   Finds the places where a curve intersects itself.

   :param rhino3dm.Curve curve: Curve for self-intersections.
   :param float tolerance: Intersection tolerance. If the curve approaches itself to within tolerance, \
      an intersection is assumed.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A collection of intersection events.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.curveCurve(curveA, curveB, tolerance, overlapTolerance, multiple=false)

   Finds the intersections between two curves.

   :param rhino3dm.Curve curveA: First curve for intersection.
   :param rhino3dm.Curve curveB: Second curve for intersection.
   :param float tolerance: Intersection tolerance. If the curves approach each other to within tolerance, \
      an intersection is assumed.
   :param float overlapTolerance: The tolerance with which the curves are tested.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A collection of intersection events.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.curveLine(curve, line, tolerance, overlapTolerance, multiple=false)

   Intersects a curve and an infinite line.

   :param rhino3dm.Curve curve: Curve for intersection.
   :param Line line: Infinite line to intesect.
   :param float tolerance: Intersection tolerance. If the curves approach each other to within tolerance, \
      an intersection is assumed.
   :param float overlapTolerance: The tolerance with which the curves are tested.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A collection of intersection events.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.curveSurface(curve, surface, tolerance, overlapTolerance, multiple=false)

   Intersects a curve and a surface.

   :param rhino3dm.Curve curve: Curve for intersection.
   :param rhino3dm.Surface surface: Surface for intersection.
   :param float tolerance: Intersection tolerance. If the curve approaches the surface to within tolerance, \
      an intersection is assumed.
   :param float overlapTolerance: The tolerance with which the curves are tested.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A collection of intersection events.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.curveSurface1(curve, curveDomain, surface, tolerance, overlapTolerance, multiple=false)

   Intersects a (sub)curve and a surface.

   :param rhino3dm.Curve curve: Curve for intersection.
   :param rhino3dm.Interval curveDomain: Domain of surbcurve to take into consideration for Intersections.
   :param rhino3dm.Surface surface: Surface for intersection.
   :param float tolerance: Intersection tolerance. If the curve approaches the surface to within tolerance, \
      an intersection is assumed.
   :param float overlapTolerance: The tolerance with which the curves are tested.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A collection of intersection events.
   :rtype: CurveIntersections
.. js:function:: RhinoCompute.Intersection.curveBrep(curve, brep, tolerance, multiple=false)

   Intersects a curve with a Brep. This function returns the 3D points of intersection
   and 3D overlap curves. If an error occurs while processing overlap curves, this function
   will return false, but it will still provide partial results.

   :param rhino3dm.Curve curve: Curve for intersection.
   :param rhino3dm.Brep brep: Brep for intersection.
   :param float tolerance: Fitting and near miss tolerance.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success, False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.curveBrep1(curve, brep, tolerance, angleTolerance, multiple=false)

   Intersect a curve with a Brep. This function returns the intersection parameters on the curve.

   :param rhino3dm.Curve curve: Curve.
   :param rhino3dm.Brep brep: Brep.
   :param float tolerance: Absolute tolerance for intersections.
   :param float angleTolerance: Angle tolerance in radians.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success, False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.curveBrepFace(curve, face, tolerance, multiple=false)

   Intersects a curve with a Brep face.

   :param rhino3dm.Curve curve: A curve.
   :param rhino3dm.BrepFace face: A brep face.
   :param float tolerance: Fitting and near miss tolerance.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success, False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.surfaceSurface(surfaceA, surfaceB, tolerance, multiple=false)

   Intersects two Surfaces.

   :param rhino3dm.Surface surfaceA: First Surface for intersection.
   :param rhino3dm.Surface surfaceB: Second Surface for intersection.
   :param float tolerance: Intersection tolerance.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success, False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.brepBrep(brepA, brepB, tolerance, multiple=false)

   Intersects two Breps.

   :param rhino3dm.Brep brepA: First Brep for intersection.
   :param rhino3dm.Brep brepB: Second Brep for intersection.
   :param float tolerance: Intersection tolerance.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success; False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.brepSurface(brep, surface, tolerance, multiple=false)

   Intersects a Brep and a Surface.

   :param rhino3dm.Brep brep: A brep to be intersected.
   :param rhino3dm.Surface surface: A surface to be intersected.
   :param float tolerance: A tolerance value.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True on success; False on failure.
   :rtype: bool
.. js:function:: RhinoCompute.Intersection.meshMeshFast(meshA, meshB, multiple=false)

   Quickly intersects two meshes. Overlaps and near misses are ignored.

   :param rhino3dm.Mesh meshA: First mesh for intersection.
   :param rhino3dm.Mesh meshB: Second mesh for intersection.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of intersection line segments, or null.
   :rtype: Line[]
.. js:function:: RhinoCompute.Intersection.meshMesh(meshes, tolerance, mode, multiple=false)

   Intersects two meshes. Overlaps and perforations are handled in the output list.

   :param list[rhino3dm.Mesh] meshes: The mesh input list. It cannot be null.
   :param float tolerance: A tolerance value. If negative, the positive value will be used.
   :param SetsCombinations mode: The required working mode.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of both intersects, and overlaps.
   :rtype: rhino3dm.Polyline[]
.. js:function:: RhinoCompute.Intersection.meshMeshAccurate(meshA, meshB, tolerance, multiple=false)

   Intersects two meshes. Overlaps and near misses are handled.

   :param rhino3dm.Mesh meshA: First mesh for intersection.
   :param rhino3dm.Mesh meshB: Second mesh for intersection.
   :param float tolerance: Intersection tolerance.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of intersection polylines.
   :rtype: rhino3dm.Polyline[]
.. js:function:: RhinoCompute.Intersection.meshRay(mesh, ray, multiple=false)

   Finds the first intersection of a ray with a mesh.

   :param rhino3dm.Mesh mesh: A mesh to intersect.
   :param Ray3d ray: A ray to be casted.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: >= 0.0 parameter along ray if successful. \
      < 0.0 if no intersection found.
   :rtype: float
.. js:function:: RhinoCompute.Intersection.meshRay1(mesh, ray, multiple=false)

   Finds the first intersection of a ray with a mesh.

   :param rhino3dm.Mesh mesh: A mesh to intersect.
   :param Ray3d ray: A ray to be casted.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: >= 0.0 parameter along ray if successful. \
      < 0.0 if no intersection found.
   :rtype: float
.. js:function:: RhinoCompute.Intersection.meshPolyline(mesh, curve, multiple=false)

   Finds the intersection of a mesh and a polyline.

   :param rhino3dm.Mesh mesh: A mesh to intersect.
   :param PolylineCurve curve: A polyline curves to intersect.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of points: one for each face that was passed by the faceIds out reference.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.meshLine(mesh, line, multiple=false)

   Finds the intersection of a mesh and a line

   :param rhino3dm.Mesh mesh: A mesh to intersect
   :param Line line: The line to intersect with the mesh
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of points: one for each face that was passed by the faceIds out reference.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.rayShoot(ray, geometry, maxReflections, multiple=false)

   Computes point intersections that occur when shooting a ray to a collection of surfaces.

   :param Ray3d ray: A ray used in intersection.
   :param list[rhino3dm.GeometryBase] geometry: Only Surface and Brep objects are currently supported. Trims are ignored on Breps.
   :param int maxReflections: The maximum number of reflections. This value should be any value between 1 and 1000, inclusive.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: An array of points: one for each face that was passed by the faceIds out reference.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.projectPointsToMeshes(meshes, points, direction, tolerance, multiple=false)

   Projects points onto meshes.

   :param list[rhino3dm.Mesh] meshes: the meshes to project on to.
   :param list[rhino3dm.Point3d] points: the points to project.
   :param rhino3dm.Vector3d direction: the direction to project.
   :param float tolerance: Projection tolerances used for culling close points and for line-mesh intersection.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: Array of projected points, or None in case of any error or invalid input.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.projectPointsToMeshesEx(meshes, points, direction, tolerance, multiple=false)

   Projects points onto meshes.

   :param list[rhino3dm.Mesh] meshes: the meshes to project on to.
   :param list[rhino3dm.Point3d] points: the points to project.
   :param rhino3dm.Vector3d direction: the direction to project.
   :param float tolerance: Projection tolerances used for culling close points and for line-mesh intersection.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: Array of projected points, or None in case of any error or invalid input.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.projectPointsToBreps(breps, points, direction, tolerance, multiple=false)

   Projects points onto breps.

   :param list[rhino3dm.Brep] breps: The breps projection targets.
   :param list[rhino3dm.Point3d] points: The points to project.
   :param rhino3dm.Vector3d direction: The direction to project.
   :param float tolerance: The tolerance used for intersections.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: Array of projected points, or None in case of any error or invalid input.
   :rtype: rhino3dm.Point3d[]
.. js:function:: RhinoCompute.Intersection.projectPointsToBrepsEx(breps, points, direction, tolerance, multiple=false)

   Projects points onto breps.

   :param list[rhino3dm.Brep] breps: The breps projection targets.
   :param list[rhino3dm.Point3d] points: The points to project.
   :param rhino3dm.Vector3d direction: The direction to project.
   :param float tolerance: The tolerance used for intersections.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: Array of projected points, or None in case of any error or invalid input.
   :rtype: rhino3dm.Point3d[]