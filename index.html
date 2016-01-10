<!doctype html>
<html>
<head>
	<title>r/BostonCeltics Box Score Generator</title>
	<link rel="stylesheet" type="text/css" href="style.css">
	<script src="jquery-1.11.2.min.js"></script>
</head>
<body>
	<h1>r/BostonCeltics Box Score Generator</h1>	
	<select id="game-list"></select> <br /><br /> <button id="boxscore-update">Generate</button>
	<input type="text" id="thread-title" onclick="this.select()"></input>
	<textarea id="boxscore-table" onclick="this.select()"></textarea>
	<script>
	//  XML to JSON
	//  Courtesy of davidwalsh.name/convert-xml-json
	function xmlToJson(xml) {
		// Create the return object
		var obj = {};
	
		if (xml.nodeType == 1) {
			if (xml.attributes.length > 0) {
			obj['@attributes'] = {};
				for (var j = 0; j < xml.attributes.length; j++) {
					var attribute = xml.attributes.item(j);
					obj["@attributes"][attribute.nodeName] = attribute.nodeValue;
				}
			}
		} else if (xml.nodeType == 3) { // text
			obj = xml.nodeValue;
		}
	
		if (xml.hasChildNodes()) {
			for(var i = 0; i < xml.childNodes.length; i++) {
				var item = xml.childNodes.item(i);
				var nodeName = item.nodeName;
				if (typeof(obj[nodeName]) == 'undefined') {
					obj[nodeName] = xmlToJson(item);
					} else {
					if (typeof(obj[nodeName].push) == 'undefined') {
						var old = obj[nodeName];
						obj[nodeName] = [];
						obj[nodeName].push(old);
					}
					obj[nodeName].push(xmlToJson(item));
				}
			}
		}
		return obj;
	};
	jQuery(document).ready(function() {
		var thisUrl = 'http://data.nba.com/data/v2015/xml/mobile_teams/nba/2015/teams/celtics_schedule.xml';
		var yql = 'http://query.yahooapis.com/v1/public/yql?q=' + encodeURIComponent('select * from xml where url="' + thisUrl + '"') + '&format=xml&callback=?';
		jQuery.getJSON(yql, function(data){
			var returnData = xmlToJson(jQuery.parseXML(data.results[0]));
			var scheduleArray = returnData.gscd.g;
			var dropdownHTML = '';
			for (var i = 0; i < scheduleArray.length; i++) {
				if (scheduleArray[i]['@attributes'].st === '3') {
						dropdownHTML = '<option value="' + scheduleArray[i]['@attributes'].gid + '">' + scheduleArray[i].v['@attributes'].tn + ' @ ' + scheduleArray[i].h['@attributes'].tn + ' (' + scheduleArray[i]['@attributes'].gdte + ')</option>' + dropdownHTML;
				}
			}
			jQuery('#game-list').empty().append(dropdownHTML);
		});
		jQuery('#boxscore-update').click(function() {
			var whichGame = jQuery('#game-list').val();
			var thisUrl = 'http://data.nba.com/data/v2015/xml/mobile_teams/nba/2015/scores/gamedetail/' + whichGame + '_gamedetail.xml';
			var yql = 'http://query.yahooapis.com/v1/public/yql?q=' + encodeURIComponent('select * from xml where url="' + thisUrl + '"') + '&format=xml&callback=?';
			jQuery.getJSON(yql, function(data) {
				var returnData = xmlToJson(jQuery.parseXML(data.results[0]));
				detailObject = returnData.g;
				celticsBox = new Object();
				celticsTeamBox = new Object();
				var celticsScore = '';
				var tableText = '';
				var officialsText = '';
				var titleText = '';
				var monthCode = {m_01:'Jan.',m_02:'Feb.',m_03:'Mar.',m_04:'Apr.',m_05:'May',m_06:'Jun.',m_07:'Jul.',m_08:'Aug.',m_09:'Sep.',m_10:'Oct.',m_11:'Nov.',m_12:'Dec.'}
				var gameCode = detailObject['@attributes'].gcode.replace('/','-');
				var gameYear = gameCode.substring(0,4);
				var gameMonthNum = 'm_' + gameCode.substring(4,6);
				var gameMonth = monthCode[gameMonthNum];
				var gameDate = gameCode.substring(6,8).replace(/^0+/, '');
				if (Number(detailObject.vls['@attributes'].s) > Number(detailObject.hls['@attributes'].s)) {
					tableText = '# ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s + ' - ' + detailObject.hls['@attributes'].s + ' ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + '\n## ' + detailObject['@attributes'].an + ' - ' + gameMonth + ' ' + gameDate + ', ' + gameYear + '\nPLAYER | MIN | FGM-A | FG% | 3PM-A | 3P% | FTM-A | FT% | OREB | DREB | REB | AST | TOV | STL | BLK | PF | +/- | PTS\n:-|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|-:';
				}
				else if (Number(detailObject.vls['@attributes'].s) < Number(detailObject.hls['@attributes'].s)) {
						tableText = '# ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s + ' - ' + detailObject.vls['@attributes'].s + ' ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + '\n## ' + detailObject['@attributes'].an + ' - ' + gameMonth + ' ' + gameDate + ', ' + gameYear + '\nPLAYER | MIN | FGM-A | FG% | 3PM-A | 3P% | FTM-A | FT% | OREB | DREB | REB | AST | TOV | STL | BLK | PF | +/- | PTS\n:-|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|-:';
				}
				if (detailObject.vls['@attributes'].ta === 'BOS') {
					celticsBox = detailObject.vls.pstsg;
					celticsTeamBox = detailObject.vls.tstsg['@attributes'];
					celticsScore = detailObject.vls['@attributes'].s;
					if (Number(detailObject.vls['@attributes'].s) > Number(detailObject.hls['@attributes'].s)) {
						titleText = 'POST GAME THREAD: ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s + ' - ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s;
					}
					else if (Number(detailObject.vls['@attributes'].s) < Number(detailObject.hls['@attributes'].s)) {
						titleText = 'THE POST GAME THREAD: ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s + ' - ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s;
					}
				}
				else if (detailObject.hls['@attributes'].ta === 'BOS') {
					celticsBox = detailObject.hls.pstsg;
					celticsTeamBox = detailObject.hls.tstsg['@attributes'];
					celticsScore = detailObject.hls['@attributes'].s;
					if (Number(detailObject.hls['@attributes'].s) > Number(detailObject.vls['@attributes'].s)) {
						if ((Number(detailObject.hls['@attributes'].s) - Number(detailObject.vls['@attributes'].s)) >= 20) {
								titleText = 'GINO TIME: ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s + ' - ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s;
						}
						else {
							titleText = 'POST GAME THREAD: ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s + ' - ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s;
						}
					}
					else if (Number(detailObject.hls['@attributes'].s) < Number(detailObject.vls['@attributes'].s)) {
						titleText = 'THE POST GAME THREAD: ' + detailObject.vls['@attributes'].tc + ' ' + detailObject.vls['@attributes'].tn + ' ' + detailObject.vls['@attributes'].s + ' - ' + detailObject.hls['@attributes'].tc + ' ' + detailObject.hls['@attributes'].tn + ' ' + detailObject.hls['@attributes'].s;
					}
				}
				for (var i = 0; i < celticsBox.length; i++) {
					var currentPlayerFGPct = 0;
					var currentPlayerTPPct = 0;
					var currentPlayerFTPct = 0;
					if (celticsBox[i]['@attributes'].fga != 0) {
						currentPlayerFGPct = Math.round(celticsBox[i]['@attributes'].fgm / celticsBox[i]['@attributes'].fga * 1000) / 10;
					}
					if (celticsBox[i]['@attributes'].tpa != 0) {
						currentPlayerTPPct = Math.round(celticsBox[i]['@attributes'].tpm / celticsBox[i]['@attributes'].tpa * 1000) / 10;
					}
					if (celticsBox[i]['@attributes'].fta != 0) {
						currentPlayerFTPct = Math.round(celticsBox[i]['@attributes'].ftm / celticsBox[i]['@attributes'].fta * 1000) / 10;
					}
					if (celticsBox[i]['@attributes'].pm > 0) {
						currentPlayerPM = '+' + celticsBox[i]['@attributes'].pm;
					}
					else {
						currentPlayerPM = celticsBox[i]['@attributes'].pm;
					}
					tableText += '\n' + celticsBox[i]['@attributes'].fn + ' ' + celticsBox[i]['@attributes'].ln + ' | ' + celticsBox[i]['@attributes'].min + ' | ' + celticsBox[i]['@attributes'].fgm + '-' + celticsBox[i]['@attributes'].fga + ' | ' + currentPlayerFGPct + '% | ' + celticsBox[i]['@attributes'].tpm + '-' + celticsBox[i]['@attributes'].tpa + ' | ' + currentPlayerTPPct + '% | ' + celticsBox[i]['@attributes'].ftm + '-' + celticsBox[i]['@attributes'].fta + ' | ' + currentPlayerFTPct + '% | ' + celticsBox[i]['@attributes'].oreb + ' | ' + celticsBox[i]['@attributes'].dreb + ' | ' + celticsBox[i]['@attributes'].reb + ' | ' + celticsBox[i]['@attributes'].ast + ' | ' + celticsBox[i]['@attributes'].tov + ' | ' + celticsBox[i]['@attributes'].stl + ' | ' + celticsBox[i]['@attributes'].blk + ' | ' + celticsBox[i]['@attributes'].pf + ' | ' + currentPlayerPM + ' | **' + celticsBox[i]['@attributes'].pts + '**';
				}
				var celticsTeamFGPct = 0;
				var celticsTeamTPPct = 0;
				var celticsTeamFTPct = 0;
				if (celticsTeamBox.fga != 0) {
					celticsTeamFGPct = Math.round(celticsTeamBox.fgm / celticsTeamBox.fga * 1000) / 10;
				}
				if (celticsTeamBox.tpa != 0) {
					celticsTeamTPPct = Math.round(celticsTeamBox.tpm / celticsTeamBox.tpa * 1000) / 10;
				}
				if (celticsTeamBox.fta != 0) {
					celticsTeamFTPct = Math.round(celticsTeamBox.ftm / celticsTeamBox.fta * 1000) / 10;
				}
				var gameOfficials = detailObject.offs.off;
				for (var i = 0; i < gameOfficials.length; i++) {
					if (i === 0) {
						officialsText += gameOfficials[i]['@attributes'].fn + ' ' + gameOfficials[i]['@attributes'].ln;
					}
					else {
						officialsText += ', ' + gameOfficials[i]['@attributes'].fn + ' ' + gameOfficials[i]['@attributes'].ln;
					}
				}
				tableText += '\n**TOTALS** | | **' + celticsTeamBox.fgm + '-' + celticsTeamBox.fga + '** | **' + celticsTeamFGPct + '%** | **' + celticsTeamBox.tpm + '-' + celticsTeamBox.tpa + '** | **' + celticsTeamTPPct + '%** | **' + celticsTeamBox.ftm + '-' + celticsTeamBox.fta + '** | **' + celticsTeamFTPct + '%** | **' + celticsTeamBox.oreb + '** | **' + celticsTeamBox.dreb + '** | **' + celticsTeamBox.reb + '** | **' + celticsTeamBox.ast + '** | **' + celticsTeamBox.tov + '** | **' + celticsTeamBox.stl + '** | **' + celticsTeamBox.blk + '** | **' + celticsTeamBox.pf + '** | | **' + celticsScore + '**\n\nFast break points: ' + celticsTeamBox.fbpts + '\n\nPoints in the paint: ' + celticsTeamBox.pip + '\n\nLargest lead: ' + celticsTeamBox.ble + '\n\nBench points: ' + celticsTeamBox.bpts + '\n\nOfficials: ' + officialsText;
				jQuery('#boxscore-table').empty().append(tableText);
				jQuery('#thread-title').val(titleText);
			});
		});
	});
	</script>
	</body>
</html>
