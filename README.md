### Plugins https://goo.gl/eHEJwm
## Installation using bash.
```
function cpas() {
	declare -a cordovaPlugins=(       
         ## http/browser
        "cordova-plugin-broadcaster"
        "cordova-plugin-http"
        "cordova-customplugin-inappbrowser"
         ## camera / Automatic License Plate Recognition 
        "cordova-plugin-camera"
        #"cordova-plugin-openalpr"
         ## audio/ Automatic speech recognition / NLP 
        "cordova-plugin-audiotoggle"
        "cordova-plugin-speechrecognition"
        "cordova-plugin-apiai"
         ## bluetooth /wifi
        "cordova-plugin-bluetoothle"
        "cordova-plugin-ble-central"
        "cordova-plugin-ble"
        "cordova-plugin-wifiinfo"
         ## Sensors / Gyro / GPS /Google Map
        "cordova-plugin-geolocation"
        "cordova-plugin-gyroscope"
        # "cordova-plugin-sso-facebook"
        # "cdv-googlemaps"
         ## IOT Connectivity
        "cordova-plugin-blinkup "
         ## Barcode 
        "manateeworks-barcodescanner-v3"
         ## Contact Books
        "cordova-plugin-contacts-phonenumbers"
         ## OpenCV
        #"cordova-plugin-image-detection"
    )
	local N_CPAs=$((${#cordovaPlugins[@]}))
    echo "Total Cordova libs  = " $N_CPAs
    echo "" > ~/.cache/CordovaLibs.db 
   	while [ $((N_CPAs )) -gt 0 ]   ;
    do
    	N_CPAs=$((N_CPAs-1))
	    echo "${N_CPAs} ${cordovaPlugins[$N_CPAs]}" >> ~/.cache/CordovaLibs.db
	    echo "[Info] cordova plugin add  ${cordovaPlugins[$N_CPAs]}"
	    cordova plugin add  ${cordovaPlugins[$N_CPAs]}
	done
	cat ~/.cache/CordovaLibs.db
}
```
