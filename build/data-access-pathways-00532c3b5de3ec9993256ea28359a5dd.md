# Data Access Considerations
The best way to access ICESat-2 data depends on your desired use case. Below, we outline some considerations and recommended data access pathways. 

**Data Product** Select an ICESat-2 [data product](https://icesat-2.gsfc.nasa.gov/science/data-products) that aligns with your goals. We recommend starting from a higher level data product and working down if necessary.

**Data Volume** Select a *local download* computing environment if you have enough disk space to store and process the data you or using; otherwise select a *cloud streaming* environment.

**Access Method** All access methods support programmatic access, but some also provide *GUIs*. We recommend using a GUI only for testing small amounts of data and programmatically accessing data in your workflows.

**Data Use Case** Choose whether you require *subsetting* (choosing specific regions or variables to download) or *interoperability* by downloading additional data from different sources using the same access method.

|Access Consideration   	|[Earthaccess](https://earthaccess.readthedocs.io/en/stable/)   	|[icepyx](https://icepyx.readthedocs.io/en/latest/)   	|[SlideRule](https://slideruleearth.io/web/rtd/) 	|
|---	|---	|---	|---	|
|Data Product |Any dataset available at [NASA Earthdata](https://www.earthdata.nasa.gov/)  	|All ICESat-2 products (except quicklooks)|ATL03, 06, 08, 13, and 24 only   	|
|Cloud Streaming  *You need compute beyond your local machine*  	|✔️[^1]   	|🔶  	|✔️ 	|
|Local Download  *You have enough memory to store and process data locally*    	|✔️   	|✔️   	| ❌ |
| Interface Type    | Python library    | Python library    | Python library or GUI |
|GUI    	|[NASA Earthdata Search](https://search.earthdata.nasa.gov/) 	|   	|[SlideRule Web Client](https://client.slideruleearth.io/)   	|
|Subsetting   	|❌  	| ❌  	|Spatial, Temporal, Variables   	|
| On-demand Data Processing | ❌  | ❌  | ✔️    |
|Other Data Products   	|   	| ARGO  	|GEDI   	|
   

## Notes
- all options require an Earthdata login

[^1]: Using xarray's `h5coro` backend is much faster than the default `h5py` backend for opening ICESat-2 granules. We recommend the following workflow when using Earthaccess in the cloud. Note this requires h5coro>=0.0.8.
    ```python
    import earthaccess
    import xarray as xr
    
    auth = earthaccess.login()
    creds = auth.get_s3_credentials(daac='NSIDC')
    results = earthaccess.search_data(short_name=<short_name>, granule_name=<granule_name>)
    url = results[0].data_links(access="direct")[0][3:] # Remove 's3:' from the beginning of the url
    ds = xr.open_dataset(url, engine='h5coro', group=<group>, credentials=creds)
    ```

🔶 in development
