racmo_interp_firn_height.py
===========================

- Interpolates and extrapolates firn heights to times and coordinates using surface splines

#### Calling Sequence
```python
from SMBcorr.racmo_interp_firn_height import interpolate_racmo_firn
interp_firn = interpolate_racmo_firn(base_dir, EPSG, 'FGRN055', tdec, X, Y,
    VARIABLE='zs', SIGMA=1.5, FILL_VALUE=np.nan)
```
[Source code](https://github.com/tsutterley/SMBcorr/blob/master/SMBcorr/racmo_interp_firn_height.py)

#### Inputs
- `base_dir`: working data directory
- `EPSG`: projection of input spatial coordinates  
- `MODEL`: model outputs to interpolate
    * `'FGRN055'`: 5.5km Greenland RACMO2.3p2
    * `'FGRN11'`: 11km Greenland RACMO2.3p2
    * `'XANT27'`: 27km Antarctic RACMO2.3p2
    * `'ASE055'`: 5.5km Amundsen Sea Embayment RACMO2.3p2
    * `'XPEN055'`: 5.5km Antarctic Peninsula RACMO2.3p2
- `tdec`: dates to interpolate in year-decimal  
- `X`: x-coordinates to interpolate in projection EPSG  
- `Y`: y-coordinates to interpolate in projection EPSG  

#### Options
- `VARIABLE`: RACMO product to interpolate  
    * `'zs'`: firn height
    * `'FirnAir'`: firn air content
- `SIGMA`: Standard deviation for Gaussian kernel  
- `FILL_VALUE`: output fill_value for invalid points  
- `REFERENCE`: calculate firn variables in reference to first field

#### Dependencies
- [numpy: Scientific Computing Tools For Python](https://numpy.org)  
- [scipy: Scientific Tools for Python](https://docs.scipy.org/doc//)  
- [netCDF4: Python interface to the netCDF C library](https://unidata.github.io/netcdf4-python/netCDF4/index.html)  
- [pyproj: Python interface to PROJ library](https://pypi.org/project/pyproj/)  
