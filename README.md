# Checkmk Factorio version monitor
This is a `drop it in and it works` Factorio version montior for your Factorio headless server. It will regularly poll 
the Factorio API to determine the latest stable version and then ask the local factorio server what version 
it is currently running. If they match, an `OK` is returned. If they don't, `CRITICAL` is returned. Error handling is done 
with `UNKNONW` response.

It'd be quite easy to call another shell script to update Factorio if the response is CRITICAL.

## Installation
`factorio_version.py` should be placed on the Factorio server in the `/lib/check_mk_agent/plugins` directory. Be sure to 
update the path to your Factorio executable. 

`factorio.py` should be placed on the checkmk server in `/opt/omd/sites/<your_checkmk_site>/local/lib/python3/cmk/base/plugins/agent_based/` directory.

Verify plugin is run by executing `check_mk_agent` on the Factorio server. It should be toward the end of the 
data reported under `<<<factorio_version>>>`.