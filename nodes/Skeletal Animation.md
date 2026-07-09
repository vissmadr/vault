---
context:
  - "[[Computer Graphics]]"
  - "[[Animation]]"
---

# Skeletal Animation

Animating 3D models using a skeleton armature.

---

There is a visible mesh, and an invisible skeleton, called an armature.
The visible mesh is bound to the armature.
The armature is made of bones.
Each vertex of the mesh is assigned weights saying how strongly each bone affects it.
When the bones move, the mesh deforms.

**Armature**: Skeleton object used to deform or animate an attached mesh.

**Bone**: One part of an armature. Bones usually represent body parts or mechanical joints.

**Skinning**: The process of connecting a mesh to armature bones so the mesh follows the skeleton. Skinning answers: "Which bones move which vertices, and by how much?"

**Rest Pose**: The default bone arrangement of an armature.

**Bind Pose**: The pose used when the mesh was bound/skinned to the skeleton.
