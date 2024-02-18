<script>
    import Label from "../atoms/Label.svelte";

    let date = new Date();
    const dayList = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
    ];
    const monthList = [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December",
    ];

    const day = dayList[date.getDay()].slice(0, 3);
    const month = monthList[date.getMonth()].slice(0, 3);
    const hour = (date.getHours() < 10 ? "0" : "") + date.getHours();
    const minute = (date.getMinutes() < 10 ? "0" : "") + date.getMinutes();
</script>

<div class="datebox">
    <Label labelMessage="{day} {date.getDate()} {month}" />
    <Label labelMessage="{hour}:{minute}" />
</div>

<style>
    .datebox {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: end;
        padding-bottom: 0.35rem;
        height: 100%;
    }
</style>
