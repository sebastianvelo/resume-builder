<script>
    import StyleSheet from "../../../../../tailwind/StyleSheet";
    export let search;

    let val;

    const style = StyleSheet("", {
        wrapper: StyleSheet("flex items-center justify-start w-full relative", {
            input: StyleSheet(
                "focus:bg-primary placeholder-black bg-primary-light p-2 w-full text-black focus:outline-none transition-500 transition-all shadow-2xl border-t border-b border-l border-gray-900"
            ),
        }),
    });
</script>

<div class={style.wrapper.get}>
    <input class={style.wrapper.input.get} type="text" bind:value={val} placeholder="Search..." />
    <button
        class={`${
            !val ? "cursor-not-allowed" : "hover:bg-primary-light"
        } py-2 px-4 rounded-br-lg rounded-tr-lg text-xl transition-all transition-500 bg-black border-2 border-black`}
        disabled={!val}
        on:click={() => search(val)}>🔎</button
    >
</div>
