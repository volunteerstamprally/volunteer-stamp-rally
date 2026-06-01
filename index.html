<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8">
      <title>スタンプ取得
      </title>

      <meta name="viewport" content="width=device-width, initial-scale=1.0">

      <script src="https://static.line-scdn.net/liff/edge/2/sdk.js">
      </script>

      <style>
        body{
          font-family:sans-serif;
          text-align:center;
          padding:20px;
          background:#f5f5f5;
          padding-bottom:260px;
        }

        .card{
          background:white;
          border-radius:12px;
          padding:20px;
          width:92%;
          max-width:500px;
          margin:auto;
          box-sizing:border-box;
        }

        .stamp{
          display:flex;
          align-items:center;
          margin:10px 0;
          padding:10px;
          border:1px solid #ddd;
          border-radius:10px;
        }

        .stamp img{
          width: 60px;
          height:60px;
          margin-right:10px;
        }

        button{
          margin-top:20px;
          padding:15px 30px;
          border:none;
          border-radius:10px;
          background:#06C755;
          color:white;
          font-size:16px;
        }
      </style>
  </head>

  <body>

    <div id="loading" style="
    padding-top:120px;
    font-size:24px;
    font-weight:bold;
    text-align:center;
    ">

      <div>
        読み込み中<span id="dots">.</span>
      </div>

      <!-- バー -->
      <div style="
        width:300px;
        height:20px;
        background:#ddd;
        border-radius:10px;
        margin:20px auto;
        overflow:hidden;
      ">

        <div id="progressBar" style="
          width:0%;
          height:100%;
          background:#06C755;
          transition:0.3s;
        "></div>

      </div>

      <!-- % -->
      <div id="progressText">
        0%
      </div>

    </div>
      
    <!-- <div class="card"> -->
    <div class="card" id="mainCard" style="display:none;">
      
      <h2 id="title">読み込み中...</h2>

      <div id="stampArea"></div>

      <!-- 回数スタンプカード -->
      <h3>🎖️ 参加回数スタンプ</h3>

      <canvas id="countBook"
      width="1536"
      height="1024"
      style="
      width:100%;
      height:auto;
      margin-top:10px;
      background:white;
      border-radius:12px;
      "></canvas>

      <!-- ジャンルスタンプカード -->
      <h3 style="margin-top:40px;">
      🌈 ジャンルスタンプ
      </h3>

      <canvas id="genreBook"
      width="1492"
      height="1054"
      style="
      width:100%;
      height:auto;
      margin-top:10px;
      background:white;
      border-radius:12px;
      "></canvas>

      </div>

      <div id="fixedButtonArea" style="
      position:fixed;
      bottom:0;
      left:0;
      width:100%;
      padding:12px;
      background:rgba(255,255,255,0.95);
      backdrop-filter:blur(6px);
      box-shadow:0 -2px 10px rgba(0,0,0,0.1);
      box-sizing:border-box;
      z-index:999;
      display:none;
      ">

        <p id="status" style="
          margin:0 0 10px 0;
          font-size:14px;
          color:#333;
          white-space:pre-line;
          text-align:left;
          max-width:500px;
          margin-inline:auto;
        "></p>

        <div id="sendProgressWrap" style="
        width:100%;
        height:14px;
        background:#ddd;
        border-radius:999px;
        overflow:hidden;
        margin:10px auto;
        max-width:500px;
        display:none;
        ">

          <div id="sendBar" style="
            width:0%;
            height:100%;
            background:#06C755;
            transition:0.3s;
          "></div>

        </div>

        <div id="sendText" style="
        font-size:13px;
        margin-bottom:10px;
        display:none;
        ">
        0%
        </div>

        <button id="btn" disabled style="
          width:100%;
          max-width:500px;
          margin:auto;
          display:block;
          padding:16px;
          border:none;
          border-radius:14px;
          background:#06C755;
          color:white;
          font-size:18px;
          font-weight:bold;
        ">
          スタンプを取得！
        </button>

      </div>

    </div>

    <script>
    // ローディングアニメ
    setInterval(()=>{

      const dots =
        document.getElementById("dots");

      if(!dots) return;

      if(dots.innerText === "."){
        dots.innerText = "..";
      }else if(dots.innerText === ".."){
        dots.innerText = "...";
      }else{
        dots.innerText = ".";
      }

    },400);

      
    const LIFF_ID = "2010258572-I9FR2Gee";
    const GAS_URL = "https://script.google.com/macros/s/AKfycbzVX1y48X2MjLmgu9-ktn5XaFgf6rNOasQESRPxlur8v7fnyFM7mlkG18nmY0ww_33J/exec";

    let userId = "";
    let spot = "";
    let sub = "";
    let stamps = [];
    let allGenres = [];
    // 画像キャッシュ
    const cachedImages = {};
      
    const stampPositions = {

      kids:[50,260],
      edu:[250,260],
      welfare_dis:[450,260],
      welfare_old:[650,260],
      health:[845,260],
      global:[1045,260],
      env:[1245,260],

      animal:[50,480],
      culture:[250,480],
      sports:[450,480],
      disaster:[650,480],
      community:[845,480],
      event:[1045,480],
      rights:[1245,480],

      studytour:[50,687],
      online:[250,687],
      seminar:[450,687],
      donation:[650,687],
      kgvnet:[845,687],
      sdgs:[1045,687],
      other:[1245,687]

    };

    const countPositions = {

      1:[80,340],
      2:[365,340],
      3:[650,340],
      4:[935,340],
      5:[1220,340],

      6:[80,595],
      7:[365,595],
      8:[650,595],
      9:[935,595],
      10:[1220,595]

    };

    async function loadImage(src){

      if(cachedImages[src]){
        return cachedImages[src];
      }

      const img = new Image();

      img.crossOrigin = "anonymous";
      
      img.src = src;

      await new Promise(r=>{
        img.onload = r;
        img.onerror = r;
      });

      cachedImages[src] = img;

      return img;

    }

    function setProgress(percent, text=""){

      document.getElementById("progressBar")
        .style.width = percent + "%";

      document.getElementById("progressText")
        .innerText =
          percent + "%" +
          (text ? " ・" + text : "");

    }

    function setSendProgress(percent,text){

      document.getElementById("sendBar")
        .style.width = percent + "%";

      document.getElementById("sendText")
        .innerText = percent + "%";

    }

    function getParam(name){
      return new URL(location.href).searchParams.get(name);
    }

    async function init(){

      // URLからspot取得
      spot = getParam("spot");

      // 取得できたら保存
      if(spot){
        sessionStorage.setItem("spot", spot);
      }

      // 消えてたら保存済みを使う
      if(!spot){
        spot = sessionStorage.getItem("spot");
      }

      console.log("① spot:", spot);

      await liff.init({
        liffId: LIFF_ID
      });

      setProgress(10,"LINEログイン");

      if(!liff.isLoggedIn()){
        liff.login();
        return;
      }

      const friendship = await liff.getFriendship();

      console.log("friendship:", friendship);
      console.log("friendFlag:", friendship.friendFlag);


      if(!friendship.friendFlag){

        document.body.innerHTML = `
          <div style="
            padding:40px;
            text-align:center;
            font-family:sans-serif;
          ">

            <h2>まずは友だち追加してください</h2>

            <p>
              スタンプラリー参加には<br>
              LINE友だち登録が必要です
            </p>

            <a
              href="https://lin.ee/w3gYAY3"
              target="_blank"
              style="
                display:inline-block;
                margin-top:20px;
                padding:15px 30px;
                background:#06C755;
                color:white;
                border-radius:12px;
                text-decoration:none;
                font-weight:bold;
              "
            >
              友だち追加する
            </a>

            <div style="
              margin:30px auto;
              max-width:320px;
              border-top:1px solid #ddd;
            "></div>

            <p style="
              color:#666;
              font-size:14px;
              margin-bottom:10px;
            ">
              追加後はこちら
            </p>

            <button
              onclick="location.reload()"
              style="
                width:100%;
                max-width:320px;
                padding:14px;
                background:#f5f5f5;
                color:#333;
                border:1px solid #ccc;
                border-radius:12px;
                font-size:16px;
                cursor:pointer;
              ">
              ここをクリック
            </button>


          </div>
        `;

        return;
      }

      // 👇ここ追加
      const profile = await liff.getProfile();
      userId = profile.userId;

      const idToken = liff.getIDToken();

      try {
        if(idToken){
          const payload = JSON.parse(atob(idToken.split('.')[1]));
          sub = payload.sub || "";
        } else {
          sub = "";
        }
      } catch(e) {
        console.log("sub取得エラー:", e);
        sub = "";
      }
      
      console.log("userId:", userId);
      console.log("sub:", sub);
      

      // スタンプ情報取得
      const res = await fetch(
        GAS_URL + "?mode=spot&spot=" + spot
      );

      const data = await res.json();

      setProgress(25,"活動情報取得");

      console.log("② data:", data);
      
      if(data.length === 0){

        document.getElementById("title")
          .innerText = "活動が見つかりません";

        return;

      }

      if(!data || data.length === 0){

        document.getElementById("title")
          .innerText = "活動が見つかりません";

        console.log("❌ data empty");

      return;
      }
      
      document.getElementById("title").innerText =
        "📍 " + data[0].activity;

      stamps = data;

      const genreRes = await fetch(
        GAS_URL + "?mode=genres"
      );

      allGenres =
        await genreRes.json();

      setProgress(50,"ボランティアジャンル情報取得");

      console.log("allGenres:", allGenres);

      if(!Array.isArray(allGenres)){
        allGenres = [];
      }

      // 取得済み確認
      let userData = [];

      try {
        const userRes = await fetch(
          GAS_URL + "?mode=user&userId=" + userId
        );
        userData = await userRes.json();

        setProgress(80,"ユーザー情報取得");

      } catch(e) {
        console.log("ユーザー取得エラー:", e);
      }

      // 表示
      // 活動名を1回だけ表示
      const titleDiv =
        document.createElement("div");

      titleDiv.innerHTML = `
        <div style="
          font-size:14px;
          color:#666;
          margin-bottom:10px;
        ">
          該当ジャンル
        </div>
      `;

      document.getElementById("stampArea")
        .appendChild(titleDiv);

      // ジャンル一覧
      data.forEach(s=>{

        const already =
          userData.includes(s.id);

        const div =
          document.createElement("div");

        div.className = "stamp";

        div.innerHTML = `
          <img src="${s.image}">

          <div style="text-align:left;">

            <b>${s.name}</b><br>

            ${
              already
              ? "⚠️ 取得済み"
              : "✅ 獲得できます"
            }

          </div>
        `;

        document.getElementById("stampArea")
          .appendChild(div);

      });

      const todayRes = await fetch(
      GAS_URL
      + "?mode=today"
      + "&userId=" + userId
      + "&spot=" + spot
      );

      const todayData =
        await todayRes.json();

      const alreadyToday =
        todayData.already;
        
        const status = document.getElementById("status");

      status.innerText = "📖 スタンプ台紙を読み込み中...";
      status.style.display = "block";

      await new Promise(r => requestAnimationFrame(()=>{
        requestAnimationFrame(r);
      }));

      const countRes = await fetch(
        GAS_URL
        + "?mode=count"
        + "&userId=" + userId
      );

      const countData =
        await countRes.json();

      const visitCount =
        countData.count || 0;

      setProgress(90,"参加回数取得");

      await drawGenreBook(userData);

      await drawCountBook(
        visitCount
      );

      setProgress(95,"現在のスタンプカード取得");

      status.innerText = "✅ 台紙読み込み完了";
        
      const allAlready = stamps.every(
        s => userData.includes(s.id)
      );

      let newGenre = false;

      stamps.forEach(s=>{

        if(!userData.includes(s.id)){
          newGenre = true;
        }

      });

      let msg = "🎁 取得できるスタンプ\n────────\n";

      if(!alreadyToday){

        msg += "✅ 回数スタンプ\n";

      }else{

        msg += "⚠️ 今日の回数スタンプは取得済み\n";

      }

      if(newGenre){

        msg += "✅ 新しいジャンルスタンプ";

      }else{

        msg += "⚠️ ジャンルは取得済み";

      }

      status.innerText = msg;
        
      const btn = document.getElementById("btn");

      if(
        !newGenre &&
        alreadyToday
      ){
        btn.style.display = "none";
      }else{
        document.getElementById(
          "fixedButtonArea"
        ).style.display = "block";
        btn.disabled = false;
      }

      // ローディング終了
      setProgress(100,"完了");

      // 100%を少し見せる
      await new Promise(r=>setTimeout(r,500));

      document.getElementById("loading")
        .style.display = "none";

      document.getElementById("mainCard")
        .style.display = "block";

    }
      
    async function drawGenreBook(userData){

      const canvas =
        document.getElementById("genreBook");;

      const ctx =
        canvas.getContext("2d");

      ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
      );
      
      // 台紙
      const base = await loadImage(
        "https://kk14universityfifth-debug.github.io/stamp-rally2/images/genrebook.png"
      );

      ctx.drawImage(base,0,0);

      // スタンプ
      for(const s of allGenres){

        if(userData.includes(s.id)){

          const img = await loadImage(s.image);

          const pos =
            stampPositions[s.id];

          ctx.drawImage(
            img,
            pos[0],
            pos[1],
            185,
            205
          );

        }

      }

    }
      
    async function drawCountBook(
      count,
      showPage = true
    ){

      const canvas =
        document.getElementById("countBook");

      const ctx =
        canvas.getContext("2d");

      ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
      );

      // 何枚目か
      let page = 1;

      let stampCount = 0;

      if(count > 0){

        page =
          Math.floor((count - 1) / 10) + 1;

        stampCount =
          ((count - 1) % 10) + 1;

      }

      // 台紙
      const base = await loadImage(
        "https://kk14universityfifth-debug.github.io/stamp-rally2/images/countbook.png"
      );

      ctx.drawImage(base,0,0);

      // 〇枚目表示
      if(showPage){

        ctx.font = "bold 60px sans-serif";

        ctx.fillStyle = "#333";

        ctx.textAlign = "left";

        ctx.fillText(
          page + "枚目",
          1250,
          950
        );
        // ctx.fillText(
        //   page + "枚目",
        //   1250,
        //   1120
        // );

      }

      // スタンプ描画
      for(let i=1;i<=stampCount;i++){

        const pos = countPositions[i];

        if(!pos) continue;

          const img = await loadImage(
            "https://kk14universityfifth-debug.github.io/stamp-rally2/images/thankyou.png"
          );

          ctx.drawImage(
            img,
            pos[0],
            pos[1],
            230,
            230
          );

      }

    }
      
    async function send(){

      const statusEl =
      document.getElementById("status");

      let dots = 0;

        statusEl.innerText = "スタンプ取得中";

        document.getElementById(
          "sendProgressWrap"
        ).style.display = "block";

        document.getElementById(
          "sendText"
        ).style.display = "block";

        setSendProgress(0,"スタンプ取得中");

      const loadingAnim = setInterval(()=>{

        dots = (dots + 1) % 4;

        statusEl.innerText =
          "スタンプ取得中" + ".".repeat(dots);

      }, 400);
      
      document.getElementById("btn")
        .disabled = true;

      document.getElementById("btn")
        .style.opacity = "0.5";
      
      // document.getElementById("status")
      //   .innerText = "スタンプ取得中...";

      try{

        console.log("fetch前");

        const formData = new URLSearchParams();

        formData.append("mode","save");

        formData.append("userId", userId);
        formData.append("sub", sub);
        formData.append("spot", spot);
        formData.append(
          "stamps",
          JSON.stringify(
            stamps.map(s=>s.id)
          )
        );

        // 最新状態で台紙を再描画
        const latestRes = await fetch(
          GAS_URL + "?mode=user&userId=" + userId
        );

        const latestUserData =
          await latestRes.json();

        // 今回取得するスタンプを追加
        stamps.forEach(s=>{

          if(!latestUserData.includes(s.id)){
            latestUserData.push(s.id);
          }

        });

        // まず保存＆LINE送信を実行
        const res = await fetch(GAS_URL,{
          method:"POST",
          body:formData
        });
        
        if(!res.ok){
          throw new Error("POST失敗");
        }

        const text = await res.text();
        
        console.log("response:", text);

        setSendProgress(25,"スタンプ取得中");
        
        // 保存後に最新回数を取得
        const latestCountRes = await fetch(
          GAS_URL
          + "?mode=count"
          + "&userId=" + userId
        );
        
        const latestCountData =
          await latestCountRes.json();
        
        const latestVisitCount =
          latestCountData.count || 0;

        setSendProgress(50,"スタンプ取得中");
        
        // 最新状態で再描画
        await drawGenreBook(latestUserData);

        // LINE送信用は〇枚目なし
        await drawCountBook(
          latestVisitCount,
          false
        );


        // canvas → 画像化
        const genreCanvas =
          document.getElementById("genreBook");

        const countCanvas =
          document.getElementById("countBook");

        const genreImage =
          genreCanvas.toDataURL(
            "image/jpeg",
            0.7
          );

        const countImage =
          countCanvas.toDataURL(
            "image/jpeg",
            0.7
          );

        // LINE送信用データ
        const sendData =
          new URLSearchParams();

        sendData.append("mode","send");

        sendData.append("userId", userId);

        sendData.append("spot", spot);

        sendData.append(
          "stamps",
          JSON.stringify(
            stamps.map(s=>s.id)
          )
        );

        sendData.append(
          "genreImage",
          genreImage
        );

        sendData.append(
          "countImage",
          countImage
        );

        setSendProgress(75,"スタンプ取得中");

        // LINE送信
        fetch(GAS_URL,{
          method:"POST",
          body:sendData
        })
        .then(r=>r.text())
        .then(t=>console.log("LINE送信:", t));

        // 画面表示用に戻す
        await drawCountBook(
          latestVisitCount,
          true
        );

        // const text = await res.text();
        // console.log("response:", text);

        clearInterval(loadingAnim);

        // 100%
        setSendProgress(100,"完了");

        // 少し見せる
        await new Promise(r=>
          setTimeout(r,400)
        );
            
        document.getElementById("status")
           .innerText = "🎉 スタンプ獲得！";

        // この瞬間にスタンプ押印
        // await drawGenreBook(latestUserData);
        
        // await drawCountBook(
        //   latestVisitCount
        // );

        document.getElementById(
          "fixedButtonArea"
        ).style.display = "none";

        document.getElementById(
          "sendProgressWrap"
        ).style.display = "none";

        document.getElementById(
          "sendText"
        ).style.display = "none";
            
      }catch(e){

        console.error("エラー:", e);

        clearInterval(loadingAnim);
            
        document.getElementById("status")
          .innerText = "エラーが発生しました";

      }

    }
      
    document.getElementById("btn")
    .onclick = send;

    init();

    </script>

  </body>
</html>
