<script lang="ts">
    import icon from "../../assets/icon.png";
    import emailIcon from "../../assets/email.svg";
    import phoneIcon from "../../assets/phone.svg";

    let intro =
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus sit amet finibus neque, in lobortis nisl. Donec rhoncus ut ex vitae venenatis. Nunc consectetur id nunc ac fringilla.";

    let defaultEducation = {
        name: "Bachelor of Example",
        location: "Example University",
        from: "July 2019",
        until: "July 2022",
    };

    let education = [structuredClone(defaultEducation)];

    let defaultEmployment = {
        name: "Software Engineer Intern",
        location: "Example Ltd.",
        from: "July 2019",
        until: "July 2022",
    };

    let employment = [structuredClone(defaultEmployment)];

    let skills = "Lorem\nIpsum\nDolor";

    let email = "john.doe@aut.ac.nz";

    let phone = "+6421234567";

    function addEducation() {
        education.push(structuredClone(defaultEducation));
        education = education;
    }

    function removeEducation(target) {
        education.splice(education.indexOf(target));
        education = education;
    }

    function addEmployment() {
        employment.push(structuredClone(defaultEmployment));
        employment = employment;
    }

    function removeEmployment(target) {
        employment.splice(employment.indexOf(target));
        employment = employment;
    }
</script>

<div>
    <div class="container">
        <div class="panel-customize">
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
                            bind:value={obj.location}
                            placeholder="Location"
                        />
                    </div>
                    <div class="below">
                        <input bind:value={obj.from} placeholder="Start date" />
                        <input bind:value={obj.until} placeholder="End date" />
                        <button
                            class="right"
                            on:click={() => removeEducation(education)}
                            >Remove</button
                        >
                    </div>
                </div>
            {/each}
            <p>Work Experience</p>
            <button on:click={addEmployment}>+ Add new</button>
            {#each employment as obj}
                <div class="group">
                    <div>
                        <input bind:value={obj.name} placeholder="Role name" />
                        <input
                            bind:value={obj.location}
                            placeholder="Organization"
                        />
                    </div>
                    <div class="below">
                        <input bind:value={obj.from} placeholder="Start date" />
                        <input bind:value={obj.until} placeholder="End date" />
                        <button
                            class="right"
                            on:click={() => removeEmployment(employment)}
                            >Remove</button
                        >
                    </div>
                </div>
            {/each}
            <p>Skills</p>
            <textarea bind:value={skills} />
            <p>Contact</p>
            <input bind:value={email} placeholder="Email" />
            <input bind:value={phone} placeholder="Phone" />
        </div>
        <div class="panel-cv">
            <div class="cv">
                <div class="header">
                    <h1>JOHN DOE</h1>
                    <h3>{email}</h3>
                    <img alt="John Doe" src={icon} />
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
                        {#if skill}
                            <p class="list">●&nbsp;&nbsp;{skill}</p>
                        {/if}
                    {/each}
                    <p class="subheader">CONTACT</p>
                    {#if email}
                        <p><img alt="Email icon" src={emailIcon} /> {email}</p>
                    {/if}
                    {#if phone}
                        <p><img alt="Phone icon" src={phoneIcon} /> {phone}</p>
                    {/if}
                </div>
            </div>
            <button class="download">Download</button>
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

    .panel-customize,
    .panel-cv {
        display: inline-block;
    }

    .panel-customize {
        flex: 1;
        margin-right: 24px;
    }

    .panel-customize input,
    .panel-customize textarea {
        font-size: 14px;
        padding: 8px;
        background-color: #fff;
        border: 1px solid #ccc;
        transition: border 0.1s ease;
    }

    .panel-customize textarea {
        resize: none;
        width: 100%;
        height: 80px;
        margin-bottom: 20px;
    }

    .panel-customize .group {
        border: 1px solid #ccc;
        padding: 8px;
        margin-bottom: 20px;
    }

    .panel-customize input {
        width: 48%;
    }

    .panel-customize .right {
        float: right;
    }

    .panel-customize .below {
        margin-top: 16px;
    }

    .panel-customize .below input {
        margin-right: 8px;
        width: 35%;
        font-size: 12px;
    }

    .panel-customize input:focus,
    .panel-customize textarea:focus {
        border: 1px solid hsl(202, 60%, 40%);
    }

    .panel-customize p {
        margin-bottom: 8px;
    }

    .panel-customize button {
        font-size: 12px;
        margin-bottom: 12px;
    }

    .panel-customize .group button {
        margin-bottom: 0;
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

    .cv .body p {
        font-size: 1.2vmin;
        font-family: "Roboto", sans-serif;
        margin-bottom: 1vmin;
        vertical-align: middle;
    }

    .cv .body .subheader {
        font-family: "Raleway", sans-serif;
        font-size: 1.5vmin;
        font-weight: 300;
    }

    .cv .body .heavy {
        font-weight: 500;
        font-size: 1.3vmin;
        margin-bottom: 0.5vmin;
    }

    .cv .body .light {
        color: #777;
    }

    .cv .body .intro {
        margin-right: 20vmin;
    }

    .cv .body img {
        height: 1.4vmin;
        vertical-align: middle;
        margin-right: 0.5vmin;
    }

    button.download {
        margin-top: 12px;
        float: right;
    }

    button {
        padding: 8px 16px;
        transition: background-color 0.2s ease;
        cursor: pointer;
        font-size: 14px;
        background-color: hsl(202, 60%, 40%);
        color: #fff;
    }

    button:hover {
        background-color: hsl(202, 60%, 50%);
    }
</style>
