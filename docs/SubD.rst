RhinoCompute.SubD
=================

.. js:module:: RhinoCompute

.. js:function:: RhinoCompute.SubD.toBrep(thisSubD, multiple=false)

   Create a Brep based on this SubD geometry

   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: rhino3dm.Brep
.. js:function:: RhinoCompute.SubD.createFromMesh(mesh, multiple=false)

   Create a new SubD from a mesh

   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: SubD
.. js:function:: RhinoCompute.SubD.createFromMesh1(mesh, options, multiple=false)

   Create a new SubD from a mesh

   :param bool multiple: (default False) If True, all parameters are expected as lists of equal length and input will be batch processed

   :rtype: SubD
