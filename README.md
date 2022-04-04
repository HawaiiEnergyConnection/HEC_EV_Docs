# ev-node
Enphase Viewer Node.js/Express API Implementation

#### Endpoint
```
https://not-implemented.com
```

## Enphase Viewer - Kumuhub Service

### GET - Search Enphase System_ID's by Address and Zipcode <br />

> Request:
> ```
> /kumuhub_service/systems/system_id?address=12-345 example St&zipcode=12345
> ```
> Response 200 - json:
> ```json
> [
>     12345,
>     54321,
>     ...
> ]
> ```

### GET - Retrieve Enlighten Manager System URL

> Request:
> ```
> /kumuhub_service/systems/{system_id}/enlighten_url
> ```
> Response 200 - str:
> ```
> https://enlighten.enphaseenergy.com/systems/123456/arrays
> ```

### GET - Retrieve Malfunctioning Microinverters

> Request:
> ```
> /kumuhub_service/systems/{system_id}/check_micros
> ```
> Response 200 - json: (only active, malfunctioning inverters) 
> ```json
> [
>     {
>         "id": 1023273222,
>         "last_report_at": 1508174262,
>         "name": "Microinverter  902167438951",
>         "serial_number": "902167438951",
>         "part_number": "800-01333-r01",
>         "sku": "IQ8A-72-2-US",
>         "model": "M250",
>         "status": "micro",
>         "active": true,
>         "status_description": "Microinverters Not Reporting"
>     }, {...}
> ]
> ```

### GET - Retrieve Malfunctioning Envoys

> Request:
> ```
> /kumuhub_service/systems/{system_id}/check_envoys
> ```
> Response 200 - json : (array: only active, malfunctioning envoys) 
> ```json
> [
>     {
>         "id": 1059563029,
>         "last_report_at": 1508174262,
>         "name": "Envoy 901553005272",
>         "serial_number": "901553005272",
>         "part_number": "800-00655-r08",
>         "sku": "ENV-IQ-AM1-240",
>         "model": "Envoy-S-Standard-NA",
>         "status": "comm",
>         "active": true
>         "status_description": "Envoy Not Reporting"
>     }, {...}
> ]
> ```

### GET - Retrieve Malfunctioning Envoys AND Microinverters

> Request:
> ```
> /kumuhub_service/systems/{system_id}/check_all
> ```
> Response 200 - json:
> ```json
> {
>     "envoys": [
>         {
>             "id": 1059563029,
>             "last_report_at": 1508174262,
>             "name": "Envoy 901553005272",
>             "serial_number": "901553005272",
>             "part_number": "800-00655-r08",
>             "sku": "ENV-IQ-AM1-240",
>             "model": "Envoy-S-Standard-NA",
>             "status": "comm",
>             "active": true
>             "status_description": "Envoy Not Reporting"
>         }, {...}
>     ],
>     "micros": [
>         {
>             "id": 1023273222,
>             "last_report_at": 1508174262,
>             "name": "Microinverter  902167438951",
>             "serial_number": "902167438951",
>             "part_number": "800-01333-r01",
>             "sku": "IQ8A-72-2-US",
>             "model": "M250",
>             "status": "micro",
>             "active": true,
>             "status_description": "Microinverters Not Reporting"
>         }, {...}
>     ]
> }
> ```
