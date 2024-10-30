# simulador-piano-javasscript-css
 Construindo um Simulador de Piano com JavaScript e CSS

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulador de Piano</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="piano">
        <div class="key white" data-note="C"></div>
        <div class="key black" data-note="C#"></div>
        <div class="key white" data-note="D"></div>
        <div class="key black" data-note="D#"></div>
        <div class="key white" data-note="E"></div>
        <div class="key white" data-note="F"></div>
        <div class="key black" data-note="F#"></div>
        <div class="key white" data-note="G"></div>
        <div class="key black" data-note="G#"></div>
        <div class="key white" data-note="A"></div>
        <div class="key black" data-note="A#"></div>
        <div class="key white" data-note="B"></div>
        <div class="key white" data-note="C2"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.piano {
    display: flex;
    flex-direction: row;
}

.key {
    width: 40px;
    height: 200px;
    margin: 2px;
    border: 1px solid #000;
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    cursor: pointer;
}

.white {
    background-color: #fff;
}

.black {
    background-color: #000;
    width: 30px;
    height: 120px;
    position: relative;
    margin-left: -15px;
    margin-right: -15px;
    z-index: 1;
}
document.addEventListener('DOMContentLoaded', () => {
    const keys = document.querySelectorAll('.key');
    const notes = {
        'C': 'sounds/C.mp3',
        'C#': 'sounds/Cs.mp3',
        'D': 'sounds/D.mp3',
        'D#': 'sounds/Ds.mp3',
        'E': 'sounds/E.mp3',
        'F': 'sounds/F.mp3',
        'F#': 'sounds/Fs.mp3',
        'G': 'sounds/G.mp3',
        'G#': 'sounds/Gs.mp3',
        'A': 'sounds/A.mp3',
        'A#': 'sounds/As.mp3',
        'B': 'sounds/B.mp3',
        'C2': 'sounds/C2.mp3'
    };

    function playNote(note) {
        const audio = new Audio(notes[note]);
        audio.play();
    }

    keys.forEach(key => {
        key.addEventListener('click', () => {
            const note = key.getAttribute('data-note');
            playNote(note);
        });
    });
});
