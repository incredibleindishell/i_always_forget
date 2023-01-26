Starting frida server on iOS device 
 frida-server -l iOS_device_IP&
 
 To list the apps running on remote 
 frida-ps -H iOS_device_IP -ai
 
<h5> Objection..... </h5>
 
` objection --gadget com.app.appmobile -N -h 192.168.56.*** explore`
