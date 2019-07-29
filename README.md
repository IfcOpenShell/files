Public test files for IfcOpenShell 
============
This is a collection of IFC files that are useful for testing [IfcOpenShell](https://github.com/IfcOpenShell/IfcOpenShell).

File name conventions
-------------

### `123.ifc`
Files that relate to an [IfcOpenShell issue](https://github.com/IfcOpenShell/IfcOpenShell/issues) are prefixed with the corresponding issue number.

### `--augmented.ifc`
Files that are augmented with quantity data from IfcOpenShell are suffixed with `--augmented`. 

The goal is to be able to run test conversions with the `--validate` option to discover geometry regressions. To augment a file with quantity data, run `IfcConvert` with `--calculate-quantities`: 

```./IfcConvert example.ifc example--augmented.ifc --calculate-quantities```

### `--accept-errors.ifc`
Files that are expected to log errors in `IfcConvert` are suffixed with `--accept-errors`. This is useful to state that there are known irregularities in a file, but that it still should be tested for segfaults. Examples are files that error in other viewers, or when other viewers don't agree on the geometry.

### `.ifc_`
Files that are prone to timeout have the file extension `.ifc_` to be able to easily exclude them from general regression testing.

### `Issue type`
It could be useful to tag the file name with the original issue type. This is not an exact science, as the issue type often changes with different versions of IfcOpenShell. Examples of common issue types:

* `--segfault`
* `--abort`
* `--timeout`
* `--no-geometry`
* `--wrong-geometry`
* `--missing-subtractions`

### `Ifc Object type`
To easily distinguish between files in a list, it is useful when the the IFC object type is tagged in the file name. E.g. `342--beam--segfault.ifc`.