function shortenURL(longUrl) {

  var key = "";
  var serviceUrl="https://www.googleapis.com/urlshortener/v1/url?key="+key;

  var options={
    muteHttpExceptions:true,
    method:"post",
    contentType: "application/json",
    payload : JSON.stringify({'longUrl': longUrl })
  };

  var response=UrlFetchApp.fetch(serviceUrl, options);

  if(response.getResponseCode() == 200) {
    var content = JSON.parse(response.getContentText());
    if ( (content != null) && (content["id"] != null) )
      return content["id"];
  }
}


function getclicks(shortUrl) {

  var key = "";
  var serviceUrl="https://www.googleapis.com/urlshortener/v1/url?key="+key+"+&shortUrl="+shortUrl+"&projection=analytics_clicks";

  var options={
    muteHttpExceptions:true,
    method:"get",
    contentType: "application/json",
  };

  var response=UrlFetchApp.fetch(serviceUrl, options);

  if(response.getResponseCode() == 200) {
    var content = JSON.parse(response.getContentText());
   return content["analytics"]["allTime"]["shortUrlClicks"]

  }
}
