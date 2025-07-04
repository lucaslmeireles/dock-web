<template>
    <span>ICON</span>
    <h2>Add truck</h2>
    <p>Complete the form bellow</p>
    <form>
        <label>Dock</label>
        <select>
            <option value="">Motores</option>
            <option value="">Assembly</option>
        </select>
        <label>Slot</label>
        <select>

        </select>
        <label>Type</label>
        <select>
            <option value="">Unload</option>
            <option value="">Load</option>
            <option value="">Unload/Load</option>
        </select>
        <label>Entry date</label>
        <input type="date" />
        <label>Entry time</label>
        <input type="time" />

        <div>
            <p>Cargo maifest</p>
            <!-- Add the cargo mainfester component-->

        </div>

        <div>
            <p>Truck</p>
            <div>
                <label>Truck name</label>
                <input type="text" placeholder="Truck name" />
                <label>Carrier</label>
                <input type="text" placeholder="Carrier name" />
                <label>Driver name</label>
                <input type="text" placeholder="Driver name" />
            </div>
        </div>
    </form>
</template>