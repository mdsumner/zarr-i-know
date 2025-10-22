# zarr-i-know

Just keeping a list of ZARR stores. 



## s3://mur-sst/zarr-v1

https://mur-sst.s3.us-west-2.amazonaws.com/zarr-v1

```
ZARR:\"/vsis3/mur-sst/zarr-v1\"
ZARR:\"/vsicurl/https://mur-sst.s3.us-west-2.amazonaws.com/zarr-v1\"
```

## s3://vzarr

https://projects.pawsey.org.au/vzarr/SEALEVEL_GLO_PHY_L4.parquet

https://projects.pawsey.org.au/vzarr/NSIDC_SEAICE_PS_S25km.parquet

https://projects.pawsey.org.au/vzarr/NSIDC_SEAICE_PS_S25km.parquet

https://projects.pawsey.org.au/vzarr/oisst-avhrr-v02r01.parquet

```
export AWS_S3_ENDPOINT=https://projects.pawsey.org.au
export AWS_NO_SIGN_REQUEST=YES
export AWS_VIRTUAL_HOSTING=FALSE

ZARR:\"/vsis3/vzarr/SEALEVEL_GLO_PHY_L4.parquet\"

ZARR:\"https://projects.pawsey.org.au/vzarr/SEALEVEL_GLO_PHY_L4.parquet\"
```

## gs://gcp-public-data-arco-era5


https://bsky.app/profile/satellitesci.bsky.social/post/3lbvo6rw7sk2j


url ?? 

```
export GS_NO_SIGN_REQUEST=YES

ZARR:/vsigs/gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3

/vsigs/gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3
```


##  Some code

GDALMultiDimRaster in {gdalraster}

```R

library(gdalraster)
Sys.setenv("GS_NO_SIGN_REQUEST"="YES")
dsn <- "ZARR:/vsigs/gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3" 
ds <- new(GDALMultiDimRaster, dsn)

js <- ds$infoAsJSON()
info <- jsonlite::fromJSON(js)
str(info)


.. .. .. ..$ : NULL
.. .. .. ..$ : NULL
.. .. .. ..$ : int 67706
.. .. ..$ attributes    :'data.frame':	4 obs. of  1 variable:
  .. .. .. ..$ calendar: chr [1:4] NA NA NA "proleptic_gregorian"
.. .. ..$ unit          : chr [1:4] NA NA NA "hours since 1900-01-01 00:00:00"
$ arrays    :List of 277
..$ latitude                                                       :List of 7
.. ..$ datatype      : chr "Float32"
.. ..$ dimensions    : chr "/latitude"
.. ..$ dimension_size: int 721
.. ..$ block_size    : int 721
.. ..$ attributes    :List of 1
.. .. ..$ long_name: chr "latitude"
.. ..$ unit          : chr "degrees_north"
.. ..$ nodata_value  : chr "NaN"
..$ level                                                          :List of 6
.. ..$ datatype      : chr "Int64"
.. ..$ dimensions    : chr "/level"
.. ..$ dimension_size: int 37
.. ..$ block_size    : int 37
.. ..$ attributes    :List of 1
.. .. ..$ long_name: chr "level"
.. ..$ unit          : chr "Hectopascal(hPa)"
..$ longitude                                                      :List of 7
.. ..$ datatype      : chr "Float32"
.. ..$ dimensions    : chr "/longitude"
.. ..$ dimension_size: int 1440
.. ..$ block_size    : int 1440
.. ..$ attributes    :List of 1


```
