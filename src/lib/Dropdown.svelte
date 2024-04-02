<script lang="ts">
    import { onMount } from "svelte";
    import type { DropdownItem } from "../types";
    import IconArrowDown from "./icons/IconArrowDown.svelte";

    export let label: string = "";
    export let options: DropdownItem[] = [];
    export let value: DropdownItem = options[0];

    let isOpen = true;
    let container: HTMLElement;
    const toggleDropdown = () => {
        isOpen = !isOpen;
    };

    const handleKeydown = (event: KeyboardEvent) => {
        if (event.key === "Enter" || event.key === " ") {
            toggleDropdown();
        }
    };

    const handleClickOutside = (event: MouseEvent) => {
        if (container && !container.contains(event.target as Node)) {
            isOpen = false;
        }
    };

    const handleOptionKeydown = (
        event: KeyboardEvent,
        option: DropdownItem
    ) => {
        if (event.key === "Enter" || event.key === " ") {
            value = option;
            toggleDropdown();
        }
    };

    onMount(() => {
        window.addEventListener("click", handleClickOutside);
        return () => {
            window.removeEventListener("click", handleClickOutside);
        };
    });
</script>

<div class="container" bind:this={container}>
    <span class="text--body-variant">{label}</span>
    <div class="dropdown">
        <div
            role="button"
            class="heading--s-variant input"
            tabindex="0"
            on:click={toggleDropdown}
            on:keydown={handleKeydown}
        >
            <span>
                {value.label}
            </span>
            <span class="icon">
                <IconArrowDown />
            </span>
        </div>
        {#if isOpen}
            <div class="dropdown__options">
                {#each options as option, index}
                    <div
                        role="button"
                        class="heading--s-variant option {index !==
                        options.length - 1
                            ? 'border'
                            : ''} {option.label === value.label
                            ? 'selected'
                            : ''}"
                        tabindex="0"
                        on:click={() => {
                            value = option;
                            toggleDropdown();
                        }}
                        on:keydown={(e) => handleOptionKeydown(e, option)}
                    >
                        {option.label}
                    </div>
                {/each}
            </div>
        {/if}
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        gap: 8px;
        width: 100%;
        max-width: 240px;
    }

    .container .input {
        padding: 18px 20px 15px;
        color: var(--color-8);
        border-radius: 4px;
        height: 48px;
        border: 1px solid var(--color-5);
        cursor: pointer;
        user-select: none;
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 8px;
    }

    .container .input:first-child {
        width: 100%;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .container .input:hover,
    .container .input:focus {
        border: 1px solid var(--color-2);
    }

    .container .input .icon {
    }

    .dropdown {
        position: relative;
    }

    .dropdown__options {
        position: absolute;
        top: 72px;
        width: 100%;
        border-radius: 8px;
        box-shadow: 0px 10px 20px 0px rgba(72, 84, 159, 0.25);
    }

    .dropdown__options .option {
        padding: 16px 24px;
        cursor: pointer;
    }

    .dropdown__options .option:hover,
    .dropdown__options .option:focus,
    .dropdown__options .option.selected {
        color: var(--color-1);
    }

    .dropdown__options .option.border {
        border-bottom: 1px solid var(--color-5);
    }
</style>
