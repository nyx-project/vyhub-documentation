# Roadmap
<iframe id="roadmap-frame" src="https://app.loopedin.io/vyhub" width="100%" height="800"
frameborder="0" onload="setIframeHeight(this)"></iframe>

<style>
    .md-sidebar--secondary {
        display: none !important;
    }
</style>

<script>
window.addEventListener('message', function (event) {
    if (event.data.hasOwnProperty("FrameHeight")) {
        console.log("bla");
        document.querySelector('#roadmap-frame').setAttribute("height", event.data.FrameHeight);
    }
});

function setIframeHeight(ifrm) {
    var height = ifrm.contentWindow.postMessage("FrameHeight", "*");
}
</script>