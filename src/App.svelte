<script>
    import Datebox from "./molecules/Datebox.svelte";
    import Statbox from "./molecules/Statbox.svelte";
    import Form from "./molecules/Form.svelte";
    import TaskList from "./molecules/TaskList.svelte";
    import { onMount } from "svelte";

    taskList = [];

    // Storing page functions
    let formWrapperHeight = "auto";
    const formWrapperHeightInit = () => {
        onMount(() => {
            const formWrapper = document.querySelector(".form_wrapper");
            if (formWrapper) {
                formWrapperHeight = formWrapper.offsetHeight + "px";
            }
        });

        return formWrapperHeight;
    };

    // Calling page functions
    formWrapperHeightInit();
</script>

<main>
    <div class="datebox_wrapper" style="height: {formWrapperHeight}">
        <Datebox />
    </div>
    <div class="statbox_wrapper">
        <Statbox labelMessage="10" isComplete />
        <Statbox labelMessage="2" />
    </div>
    <div class="form_wrapper">
        <Form on:addTask />
    </div>
    <div class="tasklist_wrapper"><TaskList {TaskList} /></div>

    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 249 1024" fill="none">
        <path
            d="M45.5416 1024H3.31216L3.31215 824.702H45.5416L45.5416 898.995H245.57L245.57 949.708H45.5416L45.5416 1024Z"
            fill="url(#paint0_linear_4_277)"
        />
        <path
            d="M245.57 793.053V848.032L3.31214 764.26L3.31214 698.144L245.57 614.491V669.469L58.6718 730.254V732.15L245.57 793.053ZM150.346 796.489L150.346 666.626H190.328V796.489H150.346Z"
            fill="url(#paint1_linear_4_277)"
        />
        <path
            d="M72.9848 472.529C63.4428 473.476 56.0299 477.545 50.7463 484.733C45.4627 491.921 42.8209 501.677 42.8209 514C42.8209 522.373 44.0038 529.443 46.3696 535.209C48.6566 540.975 51.8504 545.399 55.9511 548.48C60.0518 551.481 64.7045 552.982 69.9093 552.982C74.2466 553.14 78.0318 552.232 81.2651 550.257C84.4984 548.203 87.2979 545.399 89.6637 541.844C91.9506 538.29 93.9615 534.182 95.6964 529.522C97.3525 524.861 98.772 519.884 99.9549 514.592L105.16 492.79C107.525 482.205 110.68 472.489 114.623 463.642C118.566 454.795 123.416 447.132 129.172 440.655C134.929 434.178 141.711 429.162 149.518 425.607C157.325 421.973 166.276 420.117 176.37 420.038C191.196 420.117 204.05 423.909 214.933 431.413C225.736 438.838 234.135 449.581 240.128 463.642C246.043 477.624 249 494.488 249 514.236C249 533.827 246.003 550.889 240.01 565.423C234.017 579.879 225.145 591.175 213.395 599.311C201.566 607.368 186.937 611.595 169.509 611.99V562.343C177.632 561.79 184.414 559.46 189.855 555.352C195.218 551.165 199.279 545.596 202.039 538.645C204.72 531.615 206.061 523.676 206.061 514.829C206.061 506.14 204.799 498.596 202.276 492.198C199.752 485.72 196.243 480.704 191.748 477.15C187.253 473.595 182.087 471.818 176.252 471.818C170.81 471.818 166.237 473.437 162.53 476.676C158.824 479.835 155.669 484.496 153.067 490.657C150.465 496.74 148.099 504.204 145.97 513.052L139.345 539.474C134.377 559.934 126.61 576.087 116.042 587.936C105.475 599.785 91.2409 605.67 73.3397 605.591C58.6717 605.67 45.857 601.76 34.8955 593.861C23.934 585.883 15.3777 574.942 9.22663 561.039C3.07556 547.137 1.91018e-05 531.338 1.83297e-05 513.644C1.75437e-05 495.634 3.07555 479.914 9.22662 466.486C15.3777 452.978 23.934 442.472 34.8955 434.968C45.857 427.463 58.5534 423.593 72.9848 423.356V472.529Z"
            fill="url(#paint2_linear_4_277)"
        />
        <path
            d="M245.57 398.875L3.31213 398.875L3.31213 347.569H110.128V344.37L3.31212 257.044L3.31212 195.549L111.784 285.6L245.57 194.482L245.57 255.859L145.97 322.331L176.725 347.569H245.57V398.875Z"
            fill="url(#paint3_linear_4_277)"
        />
        <path
            d="M72.9848 52.4904C63.4427 53.4383 56.0299 57.5064 50.7463 64.6947C45.4627 71.883 42.8209 81.6386 42.8209 93.9614C42.8209 102.335 44.0038 109.404 46.3696 115.171C48.6565 120.937 51.8504 125.361 55.9511 128.442C60.0518 131.443 64.7045 132.944 69.9093 132.944C74.2466 133.102 78.0318 132.194 81.2651 130.219C84.4983 128.165 87.2979 125.361 89.6637 121.806C91.9506 118.252 93.9615 114.144 95.6964 109.483C97.3525 104.823 98.772 99.8463 99.9549 94.5538L105.16 72.7519C107.525 62.167 110.68 52.4509 114.623 43.6038C118.566 34.7566 123.416 27.0944 129.172 20.617C134.929 14.1396 141.711 9.12361 149.518 5.56895C157.325 1.9353 166.276 0.0789819 176.37 0C191.196 0.0789808 204.05 3.87061 214.933 11.3749C225.736 18.8002 234.135 29.5431 240.128 43.6038C246.043 57.5854 249 74.4503 249 94.1983C249 113.788 246.003 130.851 240.01 145.385C234.017 159.841 225.145 171.137 213.395 179.273C201.566 187.33 186.937 191.556 169.509 191.951V142.305C177.632 141.752 184.414 139.421 189.855 135.314C195.218 131.127 199.279 125.558 202.039 118.607C204.72 111.577 206.061 103.638 206.061 94.7908C206.061 86.1016 204.799 78.5579 202.275 72.1595C199.752 65.6821 196.243 60.6661 191.748 57.1114C187.253 53.5568 182.087 51.7795 176.252 51.7795C170.81 51.7795 166.237 53.3988 162.53 56.6375C158.824 59.7972 155.669 64.4577 153.067 70.6191C150.465 76.7015 148.099 84.1663 145.97 93.0135L139.345 119.436C134.377 139.895 126.609 156.049 116.042 167.898C105.475 179.747 91.2408 185.632 73.3397 185.553C58.6717 185.632 45.857 181.722 34.8955 173.823C23.934 165.844 15.3777 154.904 9.22661 141.001C3.07554 127.099 7.72145e-07 111.3 0 93.6059C-7.85933e-07 75.5956 3.07553 59.8762 9.2266 46.4475C15.3777 32.9398 23.934 22.4338 34.8955 14.9296C45.857 7.42528 58.5534 3.55466 72.9848 3.31768V52.4904Z"
            fill="url(#paint4_linear_4_277)"
        />
        <defs>
            <linearGradient
                id="paint0_linear_4_277"
                x1="3.10462"
                y1="511.163"
                x2="245.569"
                y2="511.163"
                gradientUnits="userSpaceOnUse"
            >
                <stop stop-color="#DF1B00" />
                <stop offset="1" stop-color="#FF1F00" />
            </linearGradient>
            <linearGradient
                id="paint1_linear_4_277"
                x1="3.10462"
                y1="511.163"
                x2="245.569"
                y2="511.163"
                gradientUnits="userSpaceOnUse"
            >
                <stop stop-color="#DF1B00" />
                <stop offset="1" stop-color="#FF1F00" />
            </linearGradient>
            <linearGradient
                id="paint2_linear_4_277"
                x1="3.10462"
                y1="511.163"
                x2="245.569"
                y2="511.163"
                gradientUnits="userSpaceOnUse"
            >
                <stop stop-color="#DF1B00" />
                <stop offset="1" stop-color="#FF1F00" />
            </linearGradient>
            <linearGradient
                id="paint3_linear_4_277"
                x1="3.10462"
                y1="511.163"
                x2="245.569"
                y2="511.163"
                gradientUnits="userSpaceOnUse"
            >
                <stop stop-color="#DF1B00" />
                <stop offset="1" stop-color="#FF1F00" />
            </linearGradient>
            <linearGradient
                id="paint4_linear_4_277"
                x1="3.10462"
                y1="511.163"
                x2="245.569"
                y2="511.163"
                gradientUnits="userSpaceOnUse"
            >
                <stop stop-color="#DF1B00" />
                <stop offset="1" stop-color="#FF1F00" />
            </linearGradient>
        </defs>
    </svg>
</main>

<style>
    main {
        display: grid;
        grid-template-columns: repeat(12, 1fr);
        grid-template-rows: repeat(5, 1fr);
        gap: 1rem;
        height: 100%;
        position: relative;
    }

    .form_wrapper {
        grid-column: 5 / span 6;
        grid-row: 1 / span 2;
        align-self: end;
    }

    .tasklist_wrapper {
        grid-column: 5 / span 6;
        grid-row: 4 / -1;
    }

    .datebox_wrapper {
        grid-column: 1 / span 3;
        grid-row: 1 / span 2;
        justify-self: end;
        align-self: end;
    }

    .statbox_wrapper {
        grid-column: 1 / span 3;
        grid-row: 4 / span 2;
        display: flex;
        flex-direction: column;
        gap: 2.5rem;
    }

    svg {
        position: absolute;
        top: 0;
        left: 0;
        height: 100vh;
        z-index: -1;
    }
</style>
