
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:v="urn:schemas-microsoft-com:vml">
<head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8"/>
    <title>早安公雞</title>
    <script type="text/javascript" src="http://maps.google.com/maps/api/js?sensor=false&language=zh-TW"></script>
    <script type="text/javascript">
	var g = google.maps;
	var map;
	var c= new g.LatLng(22.605964, 120.315219);//地圖中心座標
	var z = 16;//地圖縮放比例（數值越大，細節越清楚）
	var n = 4;//圓圈數
	var p = new Array();//圓心位置
	p[1] = new g.LatLng(22.605964, 120.315219);//圓心座標。以下同類各項視需要增刪
	p[2] = new g.LatLng(22.605964, 120.315219);
	p[3] = new g.LatLng(22.605964, 120.315219);
	p[4] = new g.LatLng(22.605964, 120.315219);
	var d = new Array();//半徑，單位為公尺
	d[1] = 250;
	d[2] = 450;
	d[3] = 650;
	d[4] = 850;
	var bc = '#000000';//圓周顏色
	var fc = '#87CEFA';//圓內顏色
	var ic = '';//標誌圖案；若刪除，則恢復預設標誌
	var m = new Array();//標誌物件
	var r = new Array();//圓圈物件
	var t = new Array();//標誌說明文字
	t[1] = "100元";//標誌說明文字內容。以下同類各項視需要增刪
	t[2] = "150元";
	t[3] = "200元";
	t[4] = "250元";
	var mt = '光華店';//地圖總說明
	var w = new g.InfoWindow({
		content: mt, position: c,
        })
	function addCircles() {
    		for (i = 1; i <= n; i++) {
			m[i] = new g.Marker({map: map,position: p[i],icon: ic,zIndex: 80 - i,title: t[i]});
			r[i] = new g.Circle({map: map,radius: d[i],fillColor: fc,strokeWeight: 1,strokeColor: bc});
			r[i].bindTo('center', m[i], 'position');
		}	
	}
	function load() {
		document.getElementById("map-canvas").style.width = window.innerWidth + "px";
		document.getElementById("map-canvas").style.height = window.innerHeight + "px";
		var mapDiv = document.getElementById('map-canvas');
  		map = new g.Map(mapDiv, {center: c,zoom: z,mapTypeId: g.MapTypeId.ROADMAP});
		x =addCircles();
		if(wo==true){
			w.open(map);
			if(wc==true){
				var o =setTimeout("w.close()",wt);
			}
		}
	}
     </script>
</head>
<body style="border: 0 none; margin:0; padding:0; font-family: 新細明體" onload="load()">
	<div id="map-canvas" style="width: 640px; height: 540px; margin: 0; padding:0;"></div>
 </body>

</html>​
