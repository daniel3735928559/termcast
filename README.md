# Termcast

Easily broadcast your terminal session over the network

## Usage: 

### Server live termcasting

To broadcast on port 31337: 

```./termcast```

To broadcast on port [port]:

```./termcast [port]```

To broadcast on port [port] with special socat TCP-LISTEN options:

```./termcast [port] [options]```

To, in addition, send all terminal commands to a "termcast" Slack channel:

* Create a Slack API key
* Place this key in `~/.termcast/.slack_key`
* Run `termcast` with `TC_SLACK=1`: 

```TC_SLACK=1 ./termcast [port] [options]```

### Client

To watch the termcast being broadcast, either live or by replay by ip address `$IP` on port `$PORT`:

```stty -echo; nc $IP $PORT; stty echo```

### Server replay a past termcast

To replay a previous broadcast--say started on 19700101 00:00:00:

```./tc_replay 19700101_000000```

To replay on port `$PORT`: 

```./tc_replay 19700101_000000 $PORT```

## Dependencies

`socat` must be installed.

## Side effects

The folder `~/.termcast` will be created, and files may be placed inside it.  