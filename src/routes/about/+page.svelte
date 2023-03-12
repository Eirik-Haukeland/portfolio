<script>
  import Title from "../../components/Title.svelte";
  import aLongLongTimeAgo from "../../assets/img/meFormYearsAgo.jpg"
</script>

<Title pageTitle="About page" hidden="true" />

<section aria-labelledby="aboutPageTitle">
    <h2 id="aboutPageTitle">About portfolio page</h2>
    <p>
        Welcome to my portfolio site. here you will find
        some of my better work with links to there
        repository's and if available links to a running
        example of the site of project.
    </p>
    <p>
        Fore more projects that either is unfinished or that
        i only have collaborated on and as such don not fit
        into a list of my personal projects please go to my
        <a href="https://github.com/Eirik-Haukeland">GitHub profile</a>
        and look around
    </p>
    <p>
        This portfolio page where developed with the use of
        <a href="http://www.svelte.dev">svelte</a> The
        chose of technology was made primly so that i Could
        practice for a internship later in this year.
    </p>
    <p>

    </p>
</section>

<section aria-labelledby="aboutMeTitle" id="aboutMe">
    <h2 id="aboutMeTitle">About Me</h2>
    <figure>
        <img id="photoOfPerson" src={aLongLongTimeAgo} alt="photo of Eirik B. Haukeland">
        <figcaption>Eirik B. Haukeland</figcaption>
    </figure>
    <p>
        I have been studying frontend web development at
        <a href="https://www.noroff.no/"> Noroff school of technology</a>
        for a year and have completed meny different
        project during that time.
    </p>
    <p>
        before starting my studies in web development i
        worked for meny years a a cook in various institutions
        and hotels
    </p>
</section>

<style>
    section {
        /*external style*/
        align-self: center;
        /*internal style*/
        display: grid;
        row-gap: 2rem;
        column-gap: 1rem;
        grid-auto-flow: dense;
        max-width: 30vw;
        min-width: 20rem;
        grid-template-columns: 1fr min-content;
    }

    p {
        grid-column: span 2;
    }

    p:has(+ figure) {
        grid-column: 1 / span 1;
    }

    h2, h3 {
        justify-self: center;
        grid-column: span 2;
    }

    #aboutMe {
        grid-template-columns: 1fr min-content;
        row-gap: 1em;
    }

    #aboutMe p {
        /*external*/
        grid-column: span 1;
    }

    #aboutMe p:nth-of-type(odd) {
        align-self: end;
    }

    #aboutMe > figure {
        grid-row: span 2;
    }

    figure {
        /*external*/
        grid-column: 2;
        /*internal*/
        display: grid;
        place-self: start center;
    }

    figcaption {
        justify-self: center;
    }

    #photoOfPerson {
        --img-size: 10em;
        height: var(--img-size);
        width: var(--img-size);
        object-fit: cover;
        border-radius: 50%;
    }

</style>
