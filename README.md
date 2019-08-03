﻿[![npm version](https://badge.fury.io/js/wikiapi.svg)](https://www.npmjs.com/package/wikiapi)
[![npm downloads](https://img.shields.io/npm/dm/wikiapi.svg)](https://www.npmjs.com/package/wikiapi)
[![Known Vulnerabilities](https://snyk.io/test/github/kanasimi/wikiapi/badge.svg?targetFile=package.json)](https://snyk.io/test/github/kanasimi/wikiapi?targetFile=package.json)
[![codebeat badge](https://codebeat.co/badges/47d3b442-fd49-4142-a69b-05171bf8fe36)](https://codebeat.co/projects/github-com-kanasimi-wikiapi-master)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/02aa4b9cc9df4fa9b10389abbb139ebf)](https://app.codacy.com/app/kanasimi/wikiapi?utm_source=github.com&utm_medium=referral&utm_content=kanasimi/wikiapi&utm_campaign=Badge_Grade_Dashboard)

# JavaScript MidiaWiki API
Simple way to access MidiaWiki API via JavaScript with simple wikitext parser.

## usage 運行方式
Here lists the usage of this tool.

### As node.js module
``` JavaScript
const wikiapi = require('wikiapi');

(async () => {
	let wiki = new wikiapi;
	let page = await wiki.page('ABC');
	console.log(page.wikitext);
})();
	
(async () => {
	let enwiki = new wikiapi;
	await enwiki.login('bot name', 'password', 'en');
	let page = await enwiki.page('Wikipedia:Sandbox');
	await enwiki.edit(function(page_data) {
		return page_data.wikitext
			+ '\nTest edit using {{GitHub|kanasimi/wikiapi}}.';
	}, {bot: 1});
	console.log('Done.');
})();

(async () => {
	let zhwiki = new wikiapi('zh');
	await zhwiki.login('user', 'password');
	let page = await zhwiki.page('ABC');
	page.parse().each('template',
		token => console.log(token.name));
})();

```

## Install
``` sh
npm install wikiapi
```
## OS support
| Platform    | support |
| ----------- | ------- |
| Windows     | ✔️      |
| macOS       | ✔️      |
| UNIX, Linux | ✔️      |

## See also
[wikibot](https://github.com/kanasimi/wikibot)

## Contact 聯絡我們
Contact us at [GitHub](https://github.com/kanasimi/wikiapi/issues).

[![logo](https://raw.githubusercontent.com/kanasimi/CeJS/master/_test%20suite/misc/logo.jpg)](http://lyrics.meicho.com.tw/)