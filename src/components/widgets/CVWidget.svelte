<script lang="ts">
    import icon from "../../assets/icon.png";

    let intro =
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus sit amet finibus neque, in lobortis nisl. Donec rhoncus ut ex vitae venenatis. Nunc consectetur id nunc ac fringilla.";

    let defaultEducation = {
        name: "Bachelor of Example",
        location: "Example University",
        from: "July 2019",
        until: "July 2022",
    };

    let education = [defaultEducation];

    let defaultEmployment = {
        name: "Software Engineer Intern",
        location: "Example Ltd.",
        from: "July 2019",
        until: "July 2022",
    };

    let employment = [defaultEmployment];

    let skills = "Lorem\nIpsum\nDolor";

    function addEducation() {
        education.push(defaultEducation);
        education = education;
    }

    function removeEducation(target) {
        education.splice(education.indexOf(target));
        education = education;
    }

    function addEmployment() {
        employment.push(defaultEmployment);
        employment = employment;
    }

    function removeEmployment(target) {
        employment.splice(employment.indexOf(target));
        employment = employment;
    }
</script>

<div>
    <div class="container">
        <div class="list">
            <p>Introduction</p>
            <textarea bind:value={intro} />
            <p>Education</p>
            <button on:click={addEducation}>+ Add new</button>
            {#each education as obj}
                <div class="group">
                    <div>
                        <input
                            bind:value={obj.name}
                            placeholder="Qualification name"
                        />
                        <input
                            class="right"
                            bind:value={obj.location}
                            placeholder="Location"
                        />
                    </div>
                    <div>
                        <input bind:value={obj.from} placeholder="Start date" />
                        <input
                            class="right"
                            bind:value={obj.until}
                            placeholder="End date"
                        />
                    </div>
                    <button on:click={() => removeEducation(education)}
                        >Remove</button
                    >
                </div>
            {/each}
            <p>Work Experience</p>
            <button on:click={addEmployment}>+ Add new</button>
            {#each employment as obj}
                <div class="group">
                    <div>
                        <input bind:value={obj.name} placeholder="Role name" />
                        <input
                            class="right"
                            bind:value={obj.location}
                            placeholder="Organization"
                        />
                    </div>
                    <div>
                        <input bind:value={obj.from} placeholder="Start date" />
                        <input
                            class="right"
                            bind:value={obj.until}
                            placeholder="End date"
                        />
                    </div>
                    <button on:click={() => removeEmployment(employment)}
                        >Remove</button
                    >
                </div>
            {/each}
            <p>Skills</p>

            <textarea bind:value={skills} />
        </div>
        <div class="cv">
            <div class="header">
                <h1>JOHN DOE</h1>
                <h3>john.doe@aut.ac.nz</h3>
                <img src={icon} />
            </div>
            <div class="body">
                <p class="subheader">INTRODUCTION</p>
                <p class="intro">{intro}</p>
                <p class="subheader">EDUCATION</p>
                {#each education as obj}
                    <p class="heavy">{obj.name}, {obj.location}</p>
                    <p class="light">{obj.from} - {obj.until}</p>
                {/each}
                <p class="subheader">WORK EXPERIENCE</p>
                {#each employment as obj}
                    <p class="heavy">{obj.name}, {obj.location}</p>
                    <p class="light">{obj.from} - {obj.until}</p>
                {/each}
                <p class="subheader">SKILLS</p>
                {#each skills.split("\n") as skill}
                    <p class="list">●&nbsp;&nbsp;{skill}</p>
                {/each}
                <p class="subheader">CONTACT</p>
            </div>
        </div>
    </div>
    <button class="download">Download</button>
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

    .list textarea {
        resize: none;
        width: 100%;
        height: 80px;
        margin-bottom: 20px;
    }

    .list input {
        margin-bottom: 12px;
    }

    .list input,
    .list textarea {
        font-size: 14px;
        padding: 8px;
        background-color: #fff;
        border: 1px solid #ccc;
        transition: border 0.1s ease;
    }

    .list .group {
        border: 1px solid #ccc;
        padding: 8px;
        margin-bottom: 20px;
    }

    .list input {
        width: 48%;
    }

    .list input.right {
        float: right;
    }

    .list input:focus,
    .list textarea:focus {
        border: 1px solid hsl(202, 60%, 40%);
    }

    .list p {
        margin-bottom: 8px;
    }

    .list button {
        padding: 8px 16px;
        border: 1px solid #ccc;
        background-color: #fff;
        transition: background-color 0.2s ease, border 0.2s ease;
        cursor: pointer;
        font-size: 12px;
        box-sizing: content-box;
        transition: border 0.1s ease;
        margin-bottom: 12px;
    }

    .list .group button {
        margin-bottom: 0;
    }

    .list button:hover {
        border: 1px solid hsl(202, 60%, 40%);
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

    .cv h1 {
        font-weight: 300;
        color: #444;
        font-family: "Raleway", sans-serif;
        font-size: 3vmin;
        margin-bottom: 0.8vmin;
    }

    .cv h3 {
        font-size: 1.5vmin;
        font-family: "Roboto", sans-serif;
        font-weight: 300;
        color: #777;
    }

    .cv .header img {
        position: absolute;
        top: 2.5vmin;
        right: 4vmin;
        height: 14vmin;
        border-radius: 50%;
        border: 1vmin solid #eee;
    }

    .cv .body {
        padding: 2vmin 3vmin;
    }

    .cv p {
        font-size: 1.2vmin;
        font-family: "Roboto", sans-serif;
        margin-bottom: 1vmin;
    }

    .cv .subheader {
        font-family: "Raleway", sans-serif;
        font-size: 1.5vmin;
        font-weight: 300;
    }

    .cv .heavy {
        font-weight: 500;
        font-size: 1.3vmin;
        margin-bottom: 0.5vmin;
    }

    .cv .light {
        color: #777;
    }

    .cv .intro {
        margin-right: 20vmin;
    }

    .cv .list {
        display: inline-block;
    }

    button.download {
        float: right;
        padding: 8px 16px;
        transition: background-color 0.2s ease;
        cursor: pointer;
        font-size: 14px;
        background-color: hsl(202, 60%, 40%);
        color: #fff;
        margin-top: 12px;
    }

    button.download:hover {
        background-color: hsl(202, 60%, 50%);
    }
</style>
