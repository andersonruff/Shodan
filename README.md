SHODAN DEFESA COMANDOS
# Queries para identificar câmeras com interface web
port:80 has_screenshot:true "Camera"
"Network Camera" port:80
"IP Camera" http.title:"Login"

queries/cameras/hikvision.txt
# Hikvision - buscas defensivas
product:"Hikvision"
product:"Hikvision" country:"BR"
product:"Hikvision" city:"Pouso Alegre"
"Web Version: 4.0.1"
server:Webs

queries/cameras/dahua.txt
# Dahua - buscas defensivas
product:"Dahua"
"DHIP" port:37777
"dahua" "build"

queries/cameras/rtsp.txt
# RTSP (streams)
port:554 "RTSP"
"RTSP/1.0 200 OK"
port:554 has_screenshot:true

queries/routers-onu.txt
# Routers / ONUs / GPON / EPON
"EPON" port:80
"GPON" port:80
"ZXHN" port:80
"GoAhead-Webs"

queries/dangerous-services.txt
# Serviços críticos / perigosos
port:23 "login"           # Telnet
port:21 "220"             # FTP
port:445 "smb"            # SMB
port:7547                 # TR-069 (CPE management)

queries/version-vulns.txt
# Buscar por banners/versões para correlacionar com CVE
"GoAhead-Webs/2.5.0"
"Web Version: 4.0.1"
"App-webs/2.0"
