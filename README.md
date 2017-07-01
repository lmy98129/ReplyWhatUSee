<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta content="width=device-width; initial-scale=1.0; maximum-scale=1.0; user-scalable=0" name="viewport">
    <script src="https://cdn.rawgit.com/zenorocha/clipboard.js/master/dist/clipboard.min.js"></script>
</head>
<style type="text/css">
    html,
    body {
        margin: 0px;
        height: 100%;
        text-align: center;
    }

    #bg {
        width: 100%;
        height: 100%;
        margin: 0px auto;
    }

    .container {
        display: -webkit-flex;
        display: flex;
        -webkit-flex-direction: column;
        flex-direction: "column";
        justify-content: space-around;
    }

    .btnbg {
        margin-left: 60px;
        margin-right: 60px;
        display: -webkit-flex;
        display: flex;
        -webkit-flex-direction: column;
        flex-direction: "column";
        justify-content: space-around;
    }

    .btn {
        margin-left: 30px;
        margin-right: 30px;
        border-radius:10px;
        -webkit-border-radius: 10px;
        border: solid black 0.01px;
        font-family: "华文中宋";
        font-size: 18px;
        background-color: white;
    }

    #sentence{
        font-family: "华文中宋";
        font-size: 20px;
        line-height: 30px;
    }
</style>

<body onload="I_judge()">
    <div class="container" id="bg">
        <div style="text-align:center">
            <p id="sentence">
                Loading...
            </p>
        </div>
        <div class="btnbg">
            <button class="btn" data-clipborad-action="copy" data-clipboard-target="#sentence">
            复制这段文字
            </button>
            <button class="btn" style="margin-top:15px;" onclick="window.open('.\\QR_CODE_SHOW.html')">
            我也要玩
            </button>
        </div>
    </div>

    <script>
        var btns = document.querySelectorAll('button');
        var clipboard = new Clipboard(btns);

        clipboard.on('success', function (e) {
            alert("复制成功，快去回复吧！(*^_^*)~");
            console.log(e);
        });

        clipboard.on('error', function (e) {
            console.log(e);
        });
    </script>

    <script>
        var sent = new Array();
        sent[0] = "你是我存在的理由。";
        sent[1] = "我要去有你的未来。";
        sent[2] = "你幸福所以我幸福，<br/>你快乐所以我快乐。";
        sent[3] = "对你，不管阴晴圆缺，也不变。";
        sent[4] = "当我属于你时，<br/>我才真正属于我自己。";

        function I_judge() {
            if (!window.name) {
                setSentence();
            }
            else {
                document.getElementById("sentence").innerHTML = sent[parseInt(window.name)];
            }
        }
        function setSentence() {
            var i = parseInt((Math.random() * 5) % 5);
            document.getElementById("sentence").innerHTML = sent[i];
            window.name = i;
        }
    </script>
</body>

</html>
