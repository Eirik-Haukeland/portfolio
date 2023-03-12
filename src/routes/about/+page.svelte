<script>
  import Title from "../../components/Title.svelte";
  import aLongLongTimeAgo from "../../assets/img/meFormYearsAgo.jpg"
</script>

<Title pageTitle="About page" hidden="true" />

<section aria-labelledby="aboutPageTitle">
    <h2 id="aboutPageTitle">About portfolio page</h2>
    <p>
        Welcome to my portfolio site. Here you will find
        some of my best work with links to their
        repositories and, if available, links to a running
        example of the project.
    </p>
    <p>
        For more projects that are either unfinished or that
        I only have collaborated on, and as such do not fit
        into a list of my personal projects, please go to my
        <a href="https://github.com/Eirik-Haukeland">GitHub profile</a>
        and look around
    </p>
    <p>
        This portfolio page where developed using
        <a href="http://www.svelte.dev">svelte</a>. The
        choice of technology was made primarily so that I could
        practice for an internship later in this year.
    </p>
</section>

<section aria-labelledby="aboutMeTitle" id="aboutMe">
    <h2 id="aboutMeTitle">About Me</h2>
    <figure>
        <img id="photoOfPerson" src={aLongLongTimeAgo} alt="photo of Eirik B. Haukeland">
        <figcaption>Eirik B. Haukeland</figcaption>
    </figure>
    <p>
        I have been studying front-end web development at
        <a href="https://www.noroff.no/"> Noroff School of technology and digital media</a>
        for a year and have completed many different
        projects during that time.
    </p>
    <p>
        Before starting my studies in web development, I
        worked for many years as a cook in various
        institutions and hotels.
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
        min-width: 25rem;
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

    #photoOfPerson {
        --img-size: 10em;
        height: var(--img-size);
        width: var(--img-size);
        object-fit: cover;
        border-radius: 50%;
    }

    figcaption {
        justify-self: center;
    }

    @media screen and (max-width: 400px) {
        section, #aboutMe {
            min-width: 20rem;
        }

        #aboutMe > figure {
            grid-column: 1 / span 2;
            grid-row: span 1
        }

        #photoOfPerson {
            --img-size: 15rem
        }

        #aboutMe > p {
            grid-column: 1 / span 2;
        }
    }
</style>
