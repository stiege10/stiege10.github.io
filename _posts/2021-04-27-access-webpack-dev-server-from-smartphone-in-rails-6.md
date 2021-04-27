---
title: Access webpack-dev-server from smartphone in Rails 6
tags:
- rails
- webpack
---

1. ensure your smartphone and desktop machine are in the same local network 
2. bind your rails server on the IP `0.0.0.0` when starting (e.g. `rails server -b 0.0.0.0`)
3. update the asset_host for your development environment (`environments/development.rb`)

	`config.action_controller.asset_host = 'http://<your-ip-here>:3000`
	
	if you are on a mac you can run `ipconfig getifaddr en0` in a terminal to get your local IP
	
1. restart your rails server
2. open your app on the smartphone under `http://<your-ip-here>:3000`
