/**
 * JOHN PORK BRAINROT LANGUAGE INTERPRETER
 * 
 * Runs .rot files powered by pure Rizz, Mewing, and John Pork energy.
 */

const fs = require('fs');
const readline = require('readline');

// Brainrot Tokenizer / Lexer Keywords
const KEYWORDS = {
    TALK: 'talkToThePig',
    IF: 'isItRizzing',
    ELSE: 'downInOhio',
    WHILE: 'edgeUntilSuccess',
    RETURN: 'answerTheCall',
    BREAK: 'hangUp',
    NULL: 'noAura',
};

class BrainrotInterpreter {
    constructor() {
        this.environment = {};
    }

    /**
     * Parse and run raw Brainrot code
     */
    run(code) {
        try {
            console.log("\n📞 [JOHN PORK]: Dialing into the main brainrot matrix...\n");
            
            // Clean up comments
            const cleanedCode = code.replace(/\/\/.*/g, '');

            // Convert Brainrot syntax to runnable JavaScript
            const jsCode = this.transpileToJS(cleanedCode);

            // Execute in an isolated context
            const executor = new Function('talkToThePig', 'noAura', jsCode);
            
            executor(
                (msg) => console.log(`🐷 John Pork says: "${msg}"`),
                null
            );

            console.log("\n✨ [AURA CHECK]: Execution finished with +10,000 Aura Points.");
        } catch (error) {
            this.handleOhioError(error);
        }
    }

    /**
     * Transpiles Brainrot keywords into valid JS
     */
    transpileToJS(code) {
        let js = code;

        // Keywords replacement
        js = js.replace(/isItRizzing\s*\((.*?)\)/g, 'if ($1)');
        js = js.replace(/downInOhio/g, 'else');
        js = js.replace(/edgeUntilSuccess/g, 'while (true)');
        js = js.replace(/answerTheCall\s+(.*?);/g, 'return $1;');
        js = js.replace(/hangUp;/g, 'break;');
        js = js.replace(/noAura/g, 'null');

        // Check for Fanum Tax (Memory limits simulation)
        if (js.includes('fanumTax')) {
            js = js.replace(/fanumTax\((.*?)\)/g, 'delete $1');
        }

        return js;
    }

    /**
     * Error handling themed for John Pork
     */
    handleOhioError(error) {
        console.error("\n🚨 🚨 🚨 EMERGENCY CALL FROM JOHN PORK 🚨 🚨 🚨");
        console.error("📱 [INCOMING CALL]: John Pork");
        console.error("---------------------------------------------------");
        console.error(`💥 Ohio Error Triggered: ${error.message}`);
        console.error("📉 Lost -50,000 Aura Points due to unexpected crash.");
        console.error("---------------------------------------------------\n");
    }
}

// Sample Brainrot script (used if no file provided)
const defaultBrainrotCode = `
// Definir a presença do John Pork
let porkAura = 9999;

isItRizzing(porkAura > 9000) {
    talkToThePig("John Pork is calling! Pick up the phone!");
} downInOhio {
    talkToThePig("No aura detected. Hang up.");
}

// Loop de Mewing
edgeUntilSuccess {
