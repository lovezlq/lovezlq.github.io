//判断是否是pc
function is_pc() {  
    var sUserAgent = navigator.userAgent.toLowerCase();  
    var bIsIpad = sUserAgent.match(/ipad/i) == "ipad";  
    var bIsIphoneOs = sUserAgent.match(/iphone os/i) == "iphone os";  
    var bIsMidp = sUserAgent.match(/midp/i) == "midp";  
    var bIsUc7 = sUserAgent.match(/rv:1.2.3.4/i) == "rv:1.2.3.4";  
    var bIsUc = sUserAgent.match(/ucweb/i) == "ucweb";  
    var bIsAndroid = sUserAgent.match(/android/i) == "android";  
    var bIsCE = sUserAgent.match(/windows ce/i) == "windows ce";  
    var bIsWM = sUserAgent.match(/windows mobile/i) == "windows mobile";  
    if (!(bIsIpad || bIsIphoneOs || bIsMidp || bIsUc7 || bIsUc || bIsAndroid || bIsCE || bIsWM) ){  
        return true
    } else {  
        return false 
    }  
} 
//判断是否微信登陆 
function is_wx() { 
	var ua = window.navigator.userAgent.toLowerCase(); 
	console.log(ua);//mozilla/5.0 (iphone; cpu iphone os 9_1 like mac os x) applewebkit/601.1.46 (khtml, like gecko)version/9.0 mobile/13b143 safari/601.1 
	if (ua.match(/MicroMessenger/i) == 'micromessenger') { 
		return true; 
	} else { 
		return false; 
	} 
} 

if(  is_pc() ){
	 window.location.href = 'pcURL'
}else{
	if(is_wx() === false){
		 var url = "//www.get-ticket.cn/Open/Index/index/sign/6D025DF05248D9F0920ED8A9B016389A";
		 window.location.href = url
	}
	
}
