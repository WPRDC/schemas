# WRPDC Common Schemas

This document defines the schemas for common types of datasets hosted on the WPRDC by various organizations.

### Contents
* [Datasets](#datasets)
  * [Building Permits](#building-permits)  
  * [Building Code Violations](#building-code-violations)

* [Geography Types](#geography-types)
  * [Parcel](#parcel)

# Datasets

## Building Permits
Geography type: [`parcel`](#parcel)  
Geography required: yes

#### Examples:
* [Pittsburgh Building Permtis](https://data.wprdc.org/dataset/city-of-pittsburgh-building-permits/resource/95d69895-e58d-44de-a370-fec6ad2b332e)

#### Required Fields
| Field 			| Type 		| Description																	|
|-------------------|-----------|-----------------------------------------------------------------------|
| `permit_id`      	| String	| Unique id, format likely to differ between governing body	  			|
| `permit_group`   	| String	| 'Building', 'Zoning', etc, (pgh: record_group, bldwn: Category)		|
| `permit_type`    	| String	| 'Residential', 'Commericial', etc (ph: cord_type, bldwn: cons_catg) 	|
| `permit_subtype` 	| String	| 'HVAC', 'Electrical', etc (pgh: record_type, bldwn: n/a 				|
| `issued_date`		| Date  	| Date when permit was issued											|


#### Optional Common Fields
| Field 			| Type 		| Description																	|
|-------------------|-----------|-----------------------------------------------------------------------|
| `intake_date`    	| Date		| Date when permit request rcv'd by issuer								|
| `permit_category`	| String	| More detail than `permit_type` and `permit_subtype`					|
| `status` 		   	| String	| 'Issued', 'Pending', etc											  	|
| `status_date`		| Date		| Date of most recent status change						 				|
| `last_update_date`| Date  	| Date when record was last updated										|


## Building Code Violations
Geography type:  [`parcel`](#parcel)
Geography required: yes

#### Examples:
* [Pittsburgh PLI Violations](https://data.wprdc.org/dataset/pittsburgh-pli-violations-report/resource/4e5374be-1a88-47f7-afee-6a79317019b4)

#### Required Fields
| Field 			| Type 		| Description																	|
|-------------------|-----------|-----------------------------------------------------------------------|
| `case_no`      	| String	| unique id, format likely to differ between governing body	  			|
| `violation`    	| String	| Description/ type of violation										|
| `violation_date` 	| Date  	| Date of issuance of `violation` (need for PGH)						|



#### Optional Common Fields
| Field 				| Type 		| Description																	|
|-----------------------|-----------|-----------------------------------------------------------------------|
| `inspection_result`   | String	| unique id, format likely to differ between governing body	  			|
| `inspection_date`    	| Date		| Date of inspection when violation was issued							|
| `location` 			| String  	| Location of violation on property (porch, roof, etc)					|
| `corrective_action` 	| String  	| Corrective action 													|


# Geography Types

## Parcel

#### Fields
| Field 		| Type 		| Description																	|
|---------------|-----------|-----------------------------------------------------------------------|
| `parcel_id`   | String	| Allegheny County 16-digit Parcel ID 									|
| `street`    	| String	| Street number and name												|
| `city` 		| String  	| City, municipality, township, wtc.									|
| `state` 		| String  	| US State 																|
| `latitude` 	| Float  	| latitude of parcel centroid (WGS84 projection)						|
| `longitude` 	| Float  	| longitude of parcel centroid (WGS84 projection)						|
