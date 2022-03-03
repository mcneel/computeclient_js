RhinoCompute.SubD
=================

.. js:module:: RhinoCompute

.. js:function:: RhinoCompute.SubD.joinSubDs(subdsToJoin, tolerance, joinedEdgesAreCreases, multiple=false)

   Joins an enumeration of SubDs to form as few as possible resulting SubDs.
   There may be more than one SubD in the result array.

   :param IEnumerable<SubD> subdsToJoin: An enumeration of SubDs to join.
   :param float tolerance: The join tolerance.
   :param bool joinedEdgesAreCreases: If true, merged boundary edges will be creases. \
      If false, merged boundary edges will be smooth.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: SubD[]
.. js:function:: RhinoCompute.SubD.toBrep(thisSubD, options, multiple=false)

   Create a Brep based on this SubD geometry.

   :param SubDToBrepOptions options: The SubD to Brep conversion options. Use SubDToBrepOptions.Default \
      for sensible defaults. Currently, these return unpacked faces \
      and locally-G1 vertices in the output Brep.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new Brep if successful, or None on failure.
   :rtype: rhino3dm.Brep
.. js:function:: RhinoCompute.SubD.toBrep1(thisSubD, multiple=false)

   Create a Brep based on this SubD geometry, based on SubDToBrepOptions.Default options.

   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new Brep if successful, or None on failure.
   :rtype: rhino3dm.Brep
.. js:function:: RhinoCompute.SubD.createFromMesh(mesh, multiple=false)

   Create a new SubD from a mesh.

   :param rhino3dm.Mesh mesh: The input mesh.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromMesh1(mesh, options, multiple=false)

   Create a new SubD from a mesh.

   :param rhino3dm.Mesh mesh: The input mesh.
   :param SubDCreationOptions options: The SubD creation options.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromSurface(surface, method, corners, multiple=false)

   Create a SubD that approximates the surface. If the surface is a SubD
   friendly NURBS surface and withCorners is true, then the SubD and input
   surface will have the same geometry.

   :param SubDFromSurfaceMethods method: Selects the method used to calculate the SubD.
   :param bool corners: If the surface is open, then the corner vertices with be tagged as \
      VertexTagCorner. This makes the resulting SubD have sharp corners to \
      match the appearance of the input surface.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: SubD
.. js:function:: RhinoCompute.SubD.offset(thisSubD, distance, solidify, multiple=false)

   Makes a new SubD with vertices offset at distance in the direction of the control net vertex normals.
   Optionally, based on the value of solidify, adds the input SubD and a ribbon of faces along any naked edges.

   :param float distance: The distance to offset.
   :param bool solidify: True if the output SubD should be turned into a closed SubD.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromLoft(curves, closed, addCorners, addCreases, divisions, multiple=false)

   Creates a SubD lofted through shape curves.

   :param list[rhino3dm.NurbsCurve] curves: An enumeration of SubD-friendly NURBS curves to loft through.
   :param bool closed: Creates a SubD that is closed in the lofting direction. Must have three or more shape curves.
   :param bool addCorners: With open curves, adds creased vertices to the SubD at both ends of the first and last curves.
   :param bool addCreases: With kinked curves, adds creased edges to the SubD along the kinks.
   :param int divisions: The segment number between adjacent input curves.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromSweep(rail1, shapes, closed, addCorners, roadlikeFrame, roadlikeNormal, multiple=false)

   Fits a SubD through a series of profile curves that define the SubD cross-sections and one curve that defines a SubD edge.

   :param rhino3dm.NurbsCurve rail1: A SubD-friendly NURBS curve to sweep along.
   :param list[rhino3dm.NurbsCurve] shapes: An enumeration of SubD-friendly NURBS curves to sweep through.
   :param bool closed: Creates a SubD that is closed in the rail curve direction.
   :param bool addCorners: With open curves, adds creased vertices to the SubD at both ends of the first and last curves.
   :param bool roadlikeFrame: Determines how sweep frame rotations are calculated. \
      If False (Freeform), frame are propogated based on a refrence direction taken from the rail curve curvature direction. \
      If True (Roadlike), frame rotations are calculated based on a vector supplied in "roadlikeNormal" and the world coordinate system.
   :param rhino3dm.Vector3d roadlikeNormal: If roadlikeFrame = true, provide 3D vector used to calculate the frame rotations for sweep shapes. \
      If roadlikeFrame = false, then pass .
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromSweep1(rail1, rail2, shapes, closed, addCorners, multiple=false)

   Fits a SubD through a series of profile curves that define the SubD cross-sections and two curves that defines SubD edges.

   :param rhino3dm.NurbsCurve rail1: The first SubD-friendly NURBS curve to sweep along.
   :param rhino3dm.NurbsCurve rail2: The second SubD-friendly NURBS curve to sweep along.
   :param list[rhino3dm.NurbsCurve] shapes: An enumeration of SubD-friendly NURBS curves to sweep through.
   :param bool closed: Creates a SubD that is closed in the rail curve direction.
   :param bool addCorners: With open curves, adds creased vertices to the SubD at both ends of the first and last curves.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: A new SubD if successful, or None on failure.
   :rtype: SubD
.. js:function:: RhinoCompute.SubD.mergeAllCoplanarFaces(thisSubD, tolerance, multiple=false)

   Merges adjacent coplanar faces into single faces.

   :param float tolerance: Tolerance for determining when edges are adjacent. \
      When in doubt, use the document's ModelAbsoluteTolerance property.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True if faces were merged, False if no faces were merged.
   :rtype: bool
.. js:function:: RhinoCompute.SubD.mergeAllCoplanarFaces1(thisSubD, tolerance, angleTolerance, multiple=false)

   Merges adjacent coplanar faces into single faces.

   :param float tolerance: Tolerance for determining when edges are adjacent. \
      When in doubt, use the document's ModelAbsoluteTolerance property.
   :param float angleTolerance: Angle tolerance, in radians, for determining when faces are parallel. \
      When in doubt, use the document's ModelAngleToleranceRadians property.
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :return: True if faces were merged, False if no faces were merged.
   :rtype: bool
.. js:function:: RhinoCompute.SubD.interpolateSurfacePoints(thisSubD, surfacePoints, multiple=false)

   Modifies the SubD so that the SubD vertex limit surface points are
   equal to surface_points[]

   :param rhino3dm.Point3d[] surfacePoints: point for limit surface to interpolate. surface_points[i] is the \
      location for the i-th vertex returned by SubVertexIterator vit(this)
   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: bool
