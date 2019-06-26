# my ssp

### Updated 2019.06.26

simply ssp service that select a dsp request by max bid value.

```bash
[debug] application - bidders : DspCreative(3,0.6862339310023797),DspCreative(1,0.7136300908454235),DspCreative(4,0.02866696117622103)
[debug] application - winner dsp : 1
[debug] application - bidders : DspCreative(3,0.7699494301326313),DspCreative(1,0.5012062772576434),DspCreative(4,0.1072880596640099)
[debug] application - winner dsp : 3
```

Framework, based by <a href="https://github.com/b1ueskydragon/play-samples/tree/2.7.x/play-scala-starter-example">play-scala-starter-example.</a>

## Running

```bash
$ sbt run
```

## MySQL

```bash
$ mysql.server start
$ mysql -uroot
```

`ddl/myssp_db` provide ddl and sqls for create table and columns.

## Ad site

http://localhost:9000/creative

## Remarks

### Ad Flows
1. Ad request, <b>Site -> SSP</b>
2. Bid request (with several info that helps response appropriate), <b>SSP -> DSP</b>
3. Bid response (with several info includes bid value), <b>DSP -> SSP</b>
4. A response has max bid selected by SSP. Ad response, <b>SSP -> Site</b>

At this time,
- Step 3 and 4 only Implemented
- a fake bid value is generated inside randomly :p
- automatic generation of DB / table is not available
