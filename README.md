# zarr-i-know



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


url ?? 

```
export GS_NO_SIGN_REQUEST=YES

ZARR:/vsigs/gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3

/vsigs/gcp-public-data-arco-era5/ar/full_37-1h-0p25deg-chunk-1.zarr-v3
```
