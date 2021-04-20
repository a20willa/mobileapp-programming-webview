# Rapport

Jag började med att uppdaterat namnet på appen i **strings.xml** genom att byta ut texten inom *app_name* stringen. Därefter gavs appen "internet access" (åtkomst till internet) genom att lägga till `<uses-permission android:name="android.permission.INTERNET"/>` i **mainfest.xml**.

Även tillåtelse för Javacript krävdes, vilket gjordes med följande kod i **MainActivity**.
 
    //Javascript settings  
    WebSettings webSettings = myWebView.getSettings();  
    webSettings.setJavaScriptEnabled(true);
För att skapa en WebView som appen ska använda sig av bytes helt enkelt *TextView* om till *WebView* i **content_main.xml** samt gavs ett *ID* med `android:id="@+id/my_webview"`.


Därefter skapades en private WebView i **MainActivity** med `private WebView myWebView;`. Vi lokerar sedan den ID vi skapade med denna nya private.  

    //Länkar till ID  
     myWebView = (WebView) findViewById(R.id.my_webview); 
Sist så skapas funktioner som öppnar **WebView**:

    //Pages  
    public void showExternalWebPage(){  
        myWebView.loadUrl("https://www.his.se");  
    }  
      
    public void showInternalWebPage(){  
        myWebView.loadUrl("file:///android_asset/index.html");  
    } 
 

 - Den interna hemsidan skapades lokalt i appen via en assets
 - Dessa öppnas ifrån en meny som kör respektive funktion

Internal:
![alt text](https://github.com/a20willa/mobileapp-programming-webview/blob/master/Screenshot_1618939009.png)
External:
https://github.com/a20willa/mobileapp-programming-webview/blob/master/Screenshot_1618939013.png
