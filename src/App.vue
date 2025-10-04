<template>
    <router-view />
</template>

<script>
import { setPageLocale } from "./util-frontend";
import { polyfillCountryFlagEmojis } from "country-flag-emoji-polyfill";
export default {
    created() {
        setPageLocale();
    },
};
polyfillCountryFlagEmojis();
</script>

<style>

/* ===== Nexus-Status global inline design (based on user spec) ===== */
:root{
    --bg: #0b1220; --surface:#111827; --surface-2:#0f172a; --text:#e5e7eb; --muted:#94a3b8; --border:#1f2937;
    --ok:#22c55e; --warn:#f59e0b; --down:#ef4444; --accent:#38bdf8; --radius:14px; --shadow:0 10px 30px rgba(0,0,0,.25);
}
@media (prefers-color-scheme: light){
    :root{ --bg:#f8fafc; --surface:#ffffff; --surface-2:#f1f5f9; --text:#0f172a; --muted:#475569; --border:#e2e8f0; }
}
body {
    background: radial-gradient(1200px 600px at 20% -10%, rgba(56,189,248,.15), transparent 60%), var(--bg);
    color: var(--text);
    letter-spacing: .2px;
}
a{ color:var(--accent); text-decoration:none; }
/* Cards, modals, form elements */
.card, .modal-content, .list-group-item {
    background: var(--surface) !important;
    border: 1px solid var(--border) !important;
    border-radius: var(--radius) !important;
    box-shadow: var(--shadow);
    color: var(--text);
}
.form-control, .form-select, .input-group-text {
    background: #0f172a;
    border: 1px solid var(--border);
    color: var(--text);
}
/* Navbar / Footer */
.navbar, header, footer {
    background: var(--surface-2) !important;
    border-bottom: 1px solid var(--border);
}
/* Status Badges */
.badge-ok{ color:var(--ok)!important; border:1px solid var(--border); background:rgba(34,197,94,.08); border-radius:999px; padding:.35rem .6rem;}
.badge-warn{ color:var(--warn)!important; border:1px solid var(--border); background:rgba(245,158,11,.08); border-radius:999px; padding:.35rem .6rem;}
.badge-down{ color:var(--down)!important; border:1px solid var(--border); background:rgba(239,68,68,.08); border-radius:999px; padding:.35rem .6rem;}

</style>
