# libSceAgcDriver

## add Functional

- [Non-finite DB_DEPTH_CLEAR](../../../core/libs/prx/libSceAgcDriver/Graphics/src/DepthSurface.cpp) (libSceAgcDriver) - a new depth surface whose `DB_DEPTH_CLEAR` is NaN or infinite throws, also when it would then take its plane from a live owner of the same shape or from a storage image, because its image is first cleared to that value; with a finite value a new surface without an owner or a storage image keeps the clear value as its contents rather than loading its plane from guest memory. A depth clear draw, an HTILE fast clear and an out-of-place DB expand of a pending HTILE clear with such a value throw. The value is kept as decoded, so only draws on a live depth surface that clear nothing proceed. What the DB writes or returns for a cleared tile with such a value is not measured.
