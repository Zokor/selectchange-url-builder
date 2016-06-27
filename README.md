# selectchange-url-builder
On change select option it will build an url and will redirect to the QueryString/GET option values

``` 
$('.selectListener').on('change', function () {
  url = window.location.href.split('?')[0];
  var counter = 0;
  var selfOption;
  $('.selectListener option:selected').each(function () {
    selfOption = $(this);
    if (counter == 0) {
      url += "?";
    } else {
      url += "&";
    }
    url += selfOption.parent().attr("name") + "=" + selfOption.val();
    counter += 1;
  });
  if (url) {
    window.location = url;
  }
  return false;
});
``` 
