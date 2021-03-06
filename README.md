# IP2Location CakePHP Plugin
IP2Location CakePHP plugin enables the user to find the country, region, city, coordinates, zip code, time zone, ISP, domain name, connection type, area code, weather, MCC, MNC, mobile brand name, elevation and usage type that any IP address or hostname originates from. It has been optimized for speed and memory utilization. Developers can use the API to query all IP2Location BIN databases for applications written using CakePHP.


## INSTALLATION
### For CakePHP 2.x

1. Copy the IP2Location folder to *app/Plugin*.
2. Add `CakePlugin::load('IP2Location');` to the last line of *app/Config/bootstrap.php*.
3. Download IP2Location BIN database
    - IP2Location free LITE database at http://lite.ip2location.com
    - IP2Location commercial database at http://www.ip2location.com
4. Unzip and copy the BIN file into *app/Plugin/IP2Location/data* folder. 
5. Rename the BIN file to IP2LOCATION.BIN.

### For CakePHP 3.x

1. Copy the IP2Location folder to *plugins* folder.
2. Download IP2Location BIN database
    - IP2Location free LITE database at http://lite.ip2location.com
    - IP2Location commercial database at http://www.ip2location.com
3. Unzip and copy the BIN file into *plugins/IP2Location/data* folder. 
4. Rename the BIN file to IP2LOCATION.BIN.
5. Add `use Cake\Core\Configure;` to line20 of *plugins/IP2Location/Model/IP2LocationCore.php*.

**Note:** The plugin has included an old BIN database for your testing and development purpose. 
You may want to download a latest copy of BIN database as the URL stated above.
The BIN database refers to the binary file ended with .BIN extension, but not the CSV format.
Please select the right package for download.

## USAGE
```
if (Configure::version() < '3') {
    App::uses('IP2LocationCore', 'IP2Location.Model');
}
else {
    require_once(ROOT . DS . 'plugins' . DS . 'IP2Location' . DS . 'Model' . DS . 'IP2LocationCore.php');
}

$IP2Location = new IP2LocationCore();
$record = $IP2Location->get($this->request->clientIp());

echo 'IP Address: ' . $record['ipAddress'] . '<br>';
echo 'IP Number: ' . $record['ipNumber'] . '<br>';
echo 'ISO Country Code: ' . $record['countryCode'] . '<br>';
echo 'Country Name: ' . $record['countryName'] . '<br>';
echo 'Region Name: ' . $record['regionName'] . '<br>';
echo 'City Name: ' . $record['cityName'] . '<br>';
echo 'Latitude: ' . $record['latitude'] . '<br>';
echo 'Longitude: ' . $record['longitude'] . '<br>';
echo 'ZIP Code: ' . $record['zipCode'] . '<br>';
echo 'Time Zone: ' . $record['timeZone'] . '<br>';
echo 'ISP Name: ' . $record['isp'] . '<br>';
echo 'Domain Name: ' . $record['domainName'] . '<br>';
echo 'Net Speed: ' . $record['netSpeed'] . '<br>';
echo 'IDD Code: ' . $record['iddCode'] . '<br>';
echo 'Area Code: ' . $record['areaCode'] . '<br>';
echo 'Weather Station Code: ' . $record['weatherStationCode'] . '<br>';
echo 'Weather Station Name: ' . $record['weatherStationName'] . '<br>';
echo 'MCC: ' . $record['mcc'] . '<br>';
echo 'MNC: ' . $record['mnc'] . '<br>';
echo 'Mobile Carrier Name: ' . $record['mobileCarrierName'] . '<br>';
echo 'Elevation: ' . $record['elevation'] . '<br>';
echo 'Usage Type: ' . $record['usageType'] . '<br>';
```

## SUPPORT
Email: support@ip2location.com
Website: http://www.ip2location.com
