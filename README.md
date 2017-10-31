# pex-math

[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/)

Array-based vector, quaternion and matrix math for [PEX](http://pex.gl/)

# Usage

``` javascript
// require any of the modules
var mat4 = require('pex-math/mat4')

// all of them are namespaces of functions
var identityMatrix = mat4.create()
// => [1, 0, 0, 0,
//     0, 1, 0, 0,
//     0, 0, 1, 0,
//     0, 0, 0, 1]

```

# API

## Mat4

`var mat4 = require('pex-math/mat4')`

#### mat4.create()
 Returns a 4x4 identity matrix.

 Row major memory layout:

```
 0   1   2   3
 4   5   6   7
 8   9  10  11
12  13  14  15
```

 Equivalent to the column major OpenGL spec:

```
 0   4   8  12
 1   5   9  13
 2   6  10  14
 3   7  11  15

 m00 m10 m20 m30
 m01 m11 m21 m31
 m02 m12 m22 m32
 m03 m13 m23 m33
```

Returns a new `mat4`.

#### mat4.set(a, b)
Sets a 4x4 matrix from another 4x4 matrix components.

- `a`:  mat4 - the matrix being set
- `b`:  mat4 - the matrix used as template

Returns the newly set `a`.

#### mat4.equals(a, b)
Compares two matrices.

- `a`: mat4
- `b`: mat4

Returns a `bool`.

#### mat4.copy(m)
Returns a copy of m.

- `m`: mat4

Returns a new instance of `m`.

#### mat4.mult(m, n)
Multiplies two matrices.

- `m`: mat4
- `n`: mat4

Returns `m` multipled by `n`.

#### mat4.invert(m)
Inverts a matrix.

- `m`: mat4

Returns `m` inverted.

#### mat4.tranpose(m)
Transposes a matrix.

- `m`: mat4

Returns `m` transposed.

#### mat4.identity(m)
Sets a matrix to its identity.

- `m`: mat4

Returns `m` as its identity.

#### mat4.setScale(m, v)
Sets the scale of a matrix to a vector.

- `m`: mat4
- `v`: vec3

Returns `m` modified.

#### mat4.setTranslation(m, v)
Sets the translation of a matrix to a vector.

- `m`: mat4
- `v`: vec3

Returns `m` modified.

#### mat4.setRotation(m, r, v)
Sets the rotation component of a matrix at an axis to an angle.

- `m`: mat4
- `r`: Number - the angle of rotation
- `v`: vec3 - the axis of rotation

Returns `m` modified.

#### mat4.scale(m, v)
Scales a matrix by a vector.

- `m`: mat4
- `v`: vec3

Returns `m` scaled.

#### mat4.translate(m, v)
Translates a matrix by a vector.

- `m`: mat4
- `v`: vec3

Returns `m` translated.

#### mat4.rotate(m, r, v)
Rotates a matrix by an angle at an axis

- `m`: mat4
- `r`: Number - the angle of rotation
- `v`: vec3 - the axis of rotation

Returns `m` rotated.

#### mat4.frustum(m, left, right, bottom, top, near, far)
Create a frustum matrix.

- `m`: mat4
- `left`: Number - left bound
- `right`: Number - right bound
- `bottom`: Number - bottom bound
- `top`: Number - top bound
- `near`: Number - near clipping plane
- `far`: Number - far clipping plane

Returns `m`.

#### mat4.perspective(m, fov, aspect, near, far)
Create a perspective matrix.

- `m`: mat4 - out matrix
- `fov`: Number - field of view in degrees
- `aspect`: Number - aspect ratio
- `near`: Number - near clipping plane
- `far`: Number - far clipping plane

Returns `m`.

#### mat4.ortho(m, left, right, bottom, top, near, far)
Create a orthographic matrix.

- `m`: mat4
- `left`: Number - left bound
- `right`: Number - right bound
- `bottom`: Number - bottom bound
- `top`: Number - top bound
- `near`: Number - near clipping plane
- `far`: Number - far clipping plane

Returns `m`.

#### mat4.lookAt(m, from, to, up)
Calculates a lookAt matrix from a position, target and up vectors.

- `m`: mat4
- `from`: vec3 - position vector
- `to`: vec3 - target vector
- `up`: vec3 - up vector

Returns `m`.

#### mat4.fromQuat(m, q)
Sets matrix to a quaternion

- `m`: mat4
- `q`: quat

Returns `m`.

#### mat4.fromMat3(m4, m3)
Sets a 4x4 matrix to a 3x3 matrix.

- `m4`: mat4
- `m3`: mat3

Returns `m4`.
