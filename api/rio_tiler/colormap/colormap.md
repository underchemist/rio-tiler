# Module rio_tiler.colormap

rio-tiler colormap functions and classes.

None

## Variables

```python3
DEFAULT_CMAPS_FILES
```

```python3
EMPTY_COLORMAP
```

```python3
USER_CMAPS_DIR
```

```python3
cmap
```

## Functions

    
### apply_cmap

```python3
def apply_cmap(
    data: numpy.ndarray,
    colormap: Dict
) -> Tuple[numpy.ndarray, numpy.ndarray]
```

    
Apply colormap on data.

**Parameters:**

| Name | Type | Description | Default |
|---|---|---|---|
| data | numpy ndarray | 1D image array to translate to RGB. | None |
| colormap | dict | GDAL RGBA Color Table dictionary. | None |

**Returns:**

| Type | Description |
|---|---|
| tuple | Data (numpy.ndarray) and Mask (numpy.ndarray) values. |

**Raises:**

| Type | Description |
|---|---|
| InvalidFormat | If data is not a 1 band dataset (1, col, row). |

    
### apply_discrete_cmap

```python3
def apply_discrete_cmap(
    data: numpy.ndarray,
    colormap: Dict
) -> Tuple[numpy.ndarray, numpy.ndarray]
```

    
Apply discrete colormap.

**Parameters:**

| Name | Type | Description | Default |
|---|---|---|---|
| data | numpy ndarray | 1D image array to translate to RGB. | None |
| color_map | dict | Discrete ColorMap dictionary. | None |

**Returns:**

| Type | Description |
|---|---|
| tuple | Data (numpy.ndarray) and Alpha band (numpy.ndarray). |

    
### make_lut

```python3
def make_lut(
    colormap: Dict
) -> numpy.ndarray
```

    
Create a lookup table numpy.ndarray from a GDAL RGBA Color Table dictionary.

**Parameters:**

| Name | Type | Description | Default |
|---|---|---|---|
| colormap | dict | GDAL RGBA Color Table dictionary. | None |

**Returns:**

| Type | Description |
|---|---|
| numpy.ndarray | colormap lookup table. |

## Classes

### ColorMaps

```python3
class ColorMaps(
    data: Dict[str, Union[str, <built-in function array>]] = NOTHING
)
```

#### Attributes

| Name | Type | Description | Default |
|---|---|---|---|
| data | dict | colormaps. Defaults to `rio_tiler.colormap.DEFAULTS_CMAPS`. | `rio_tiler.colormap.DEFAULTS_CMAPS` |

#### Methods

    
#### get

```python3
def get(
    self,
    name: str
) -> Dict
```

    
Fetch a colormap.

**Parameters:**

| Name | Type | Description | Default |
|---|---|---|---|
| name | dict | colormap name.
Returns | None |
| dict | None | colormap dictionary. | None |

    
#### list

```python3
def list(
    self
) -> List[str]
```

    
List registered Colormaps.

Returns
    list: list of colormap names.

    
#### register

```python3
def register(
    self,
    custom_cmap: Dict[str, Union[str, Dict]],
    overwrite: bool = False
) -> 'ColorMaps'
```

    
Register a custom colormap.

**Parameters:**

| Name | Type | Description | Default |
|---|---|---|---|
| custom_cmap | dict | custom colormap(s) to register. | None |
| overwrite | bool | Overwrite existing colormap with same key (default: False) | None |