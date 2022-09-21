<script lang="ts">
    import icon from "../../assets/icon.png";
</script>

<div class="container">
    <div class="list">
        <button class="download">Download</button>
    </div>
    <div class="cv">
        <div class="header">
            <h1>JOHN DOE</h1>
            <h3>ENGINEERING STUDENT</h3>
            <img src={icon} />
        </div>
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        align-items: stretch;
        width: 100%;
    }

    .list,
    .cv {
        display: inline-block;
    }

    .list {
        flex: 1;
        margin-right: 24px;
    }

    .cv {
        position: relative;
        height: 75vh;
        aspect-ratio: 1 / 1.4142;
        background-color: #fff;
        border: 1px solid #ddd;
    }

    .cv .header {
        background-color: #eee;
        padding: 2vmin 3vmin;
    }

    .cv h1,
    h2,
    h3 {
        font-weight: 300;
        color: #444;
        font-family: "Raleway", sans-serif;
    }

    .cv h1 {
        font-size: 3vmin;
        margin-bottom: 0.8vmin;
    }

    .cv h2 {
        font-size: 2vmin;
    }

    .cv h3 {
        font-size: 1.5vmin;
    }

    .cv .header img {
        position: absolute;
        top: 2.5vmin;
        right: 4vmin;
        height: 14vmin;
        border-radius: 50%;
        border: 1vmin solid #eee;
    }

    button.download {
        float: right;
        padding: 8px 16px;
        transition: background-color 0.2s ease;
        cursor: pointer;
        font-size: 14px;
        background-color: hsl(202, 60%, 40%);
        color: #fff;
        margin-left: 12px;
    }

    button.download:hover {
        background-color: hsl(202, 60%, 50%);
    }
</style>
