# Projects
JS Calculator
Step 1: Using html, CSS and JS
Step 2: Create HTML:
    <div class="bg-image"></div>
    <div class="calculator-grid">
        <div class="output">
            <div data-previous-operand class="previous-operand"></div>
            <div data-current-operand class="previous-operand"></div>
        </div>
        <button data-all-clear class="span-two">Ac</button>
        <button data-delete>DEL</button>
        <button data-operation>÷</button>
        <button data-number>1</button>
        <button data-number>2</button>
        <button data-number>3</button>
        <button data-operation>*</button>
        <button data-number>4</button>
        <button data-number>5</button>
        <button data-number>6</button>
        <button data-operation>+</button>
        <button data-number>7</button>
        <button data-number>8</button>
        <button data-number>9</button>
        <button data-operation>-</button>
        <button data-number>.</button>
        <button data-number>0</button>
        <button data-equal class="span-two">=</button>
    </div>
Step 3: Worked on the styling:
    /* body{
    background-color: azure;
    } */
    
    .bg-image{
        background-image: url("../images/anime\ background.png");
        height: 100vh;
        width: 100%;
        /* filter: blur(1px);
        -webkit-filter: blur(1px); */
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }
    
    .calculator-grid{
        display: grid;
        justify-content: center;
        align-content: center;
        min-height: 100vh;
        grid-template-columns: repeat(4, 100px);
        grid-template-rows: minmax(120, auto) repeat(5, 100px);
        position: absolute;
        top: 40%;
        left: 40%;
        transform: translate(-50%, -50%);
        width: 80%;
        padding: 20px;
        text-align: center;
    }
    
    .calculator-grid>button{
        cursor: pointer;
        font-size: 1.3rem;
        border: 1px solid green;
        outline: none;
        background-color: darkturquoise;
        border-radius: 20px;
        height: 50px;
        transition: background-color .3s;
    }
    
    .calculator-grid>button:hover{
        background-color: rgb(0, 191, 255);
        color: white;
    }
    
    .span-two {
        grid-column: span 2;
    }
    
    .output {
        grid-column: 1/-1;
        background-color: white;
        display: flex;
        align-items: flex-end;
        justify-content: space-around;
        flex-direction: column;
        padding: 20px;
        word-wrap: break-word;
        word-break: break-all;
        border-radius: 15px;
    }
    
    .output .previous-operand {
        color: black;
        font-size: 1.5rem;
    }
    
    .output .current-operand {
        color: gold;
        font-size: 1.5rem;
    }

Step 4: Link JS in html
Step 4.1: Select all the html elements - done
    const numberButtons = document.querySelectorAll('[data-number]')
    const operationButtons = document.querySelectorAll('[data-operation]')
    const equalsButton = document.querySelector('[data-equal]')
    const deleteButton = document.querySelector('[data-delete]')
    const clearButton = document.querySelector('[data-all-clear]')
    const previousOperandTextElement = document.querySelector('[data-previous-operand]')
    const currentOperandTextElement = document.querySelector('[data-current-operand]')
Step 4.2: Create a calculator class
    Step 4.2.1: Create methods for the calculator:
        4.2.1.a Clear()
        4.2.1.b delete()
        4.2.1.c appendNumber()
        4.2.1.d chooseOperation()
        4.2.1.e compute()
        4.2.1.f getDisplayNumber()
        4.2.1.g updateDisplay()