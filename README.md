# Piwik GeoIP2 Plugin

## Description

This plugin adds support for [MaxMind GeoIP2](https://www.maxmind.com/en/geoip2-services-and-databases) database.

As i donot know how to chain the LocationProvider in Pivik i added the Intranet IPAM lookup to an existing Location Provider

Currently supported databases:

* GeoIP2-City.mmdb
* GeoLite2-City.mmdb
* GeoIP2-Country.mmdb
* GeoLite2-Country.mmdb

## [How do i get GeoIP2 databases](https://github.com/diabl0/piwik-geoip2/wiki/How-do-I-get-the-GeoIP-2-databases%3F)

## [FAQ](https://github.com/diabl0/piwik-geoip2/wiki/FAQ)

## [Intranet Data lookup] (https://github.com/grzchr15/piwik-geoip2/wiki/IntranetLookup)

Sample database
<pre>
<?php
/**
 * @author https://github.com/ThaDafinser
 * @author https://github.com/grzchr15
 */
/**
 * Here you can add your subnetworks and their location based informations
 * 
 * visitorInfo can be extended to all available fields inside the `log_visit` table of piwik
 *
    const CONTINENT_CODE_KEY = 'continent_code'; 
    const CONTINENT_NAME_KEY = 'continent_name';
    const COUNTRY_CODE_KEY = 'country_code';
    const COUNTRY_NAME_KEY = 'country_name';
    const REGION_CODE_KEY = 'region_code';  -> either MAXMIND region codes or own region codes
    const REGION_NAME_KEY = 'region_name'; -> either MAXMIND region names or own region names
    const CITY_NAME_KEY = 'city_name';
    const AREA_CODE_KEY = 'area_code';
    const LATITUDE_KEY = 'lat';
    const LONGITUDE_KEY = 'long';
    const POSTAL_CODE_KEY = 'postal_code';
    const ISP_KEY = 'isp';
    const ORG_KEY = 'org';
*/
return [
    /*
     * Use your IPAM ( Ip-Adddress database) to create this file
     * You can also apply here all possible visitorInformation data if you want
     */
	['visitorInfo' => [
		'continent_code' => '',
		'continent_name' => '',
		'country_code' => 'AT',
		'region_code' => 'AT-01-01'
		'region_name' => 'Office Graz'
		'city_name' => 'Graz',
		'area_code' => 'Styria',
		'postal_code' => '8045',
		'location_latitude' => '47.076722',
		'location_longitude' => '15.437309',
		'isp' => 'Some Company',
		'org' => 'Some organisation at your site',
		],
	'networks' => [		'2001:db8:1234::/56',
			'172.16.22.0/24'
	]
],
	['visitorInfo' => [
		'continent_code' => '',
		'continent_name' => '',
		'country_code' => 'AT',
		'region_code' => 'AT-01-01'
		'region_name' => 'Office Graz'
		'city_name' => 'Graz',
		'area_code' => 'Styria',
		'postal_code' => '8045',
		'location_latitude' => '47.074475',
		'location_longitude' => '15.392761',
		'isp' => 'Some other Company',
		'org' => 'Some other organisation at your site',
		],
	'networks' => [		'2001:db8:5678::/56',
			'172.16.23.0/24'
	]
]
];
</pre>