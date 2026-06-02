import React, { useContext } from "react";
import "./App.css";
import { dataContext } from "./context/UserContext";
import speak from "./assets/speak.gif";
import listening from "./assets/aiVoice.gif";

function App() {
  let {
    recognition,
    speaking,
    setSpeaking,
    prompt,
    response,
    setPrompt,
    setResponse,
  } = useContext(dataContext);

  return (
    <div className="main">
      <div className="bg-grid" />
      <div className="scanline" />

      <div className="hud-corner top-left">
        <span>SYS</span><span>ONLINE</span>
      </div>
      <div className="hud-corner top-right">
        <span>AI</span><span>v2.5</span>
      </div>

      <div className="center-wrap">
        <div className="title-block">
          <p className="label-tag">ASHIK</p>
          <h1 className="title">VOICE<br /><span>ASSISTANT</span></h1>
        </div>

        {!speaking ? (
          <div className="idle-state">
            <div className="orb-container">
              <div className="orb-ring ring1" />
              <div className="orb-ring ring2" />
              <div className="orb-ring ring3" />
              <button
                className="orb-btn"
                onClick={() => {
                  recognition.stop();
                  setPrompt("Listening...");
                  setSpeaking(true);
                  setResponse(false);
                  recognition.start();
                }}
              >
                <span className="mic-icon">🎙</span>
              </button>
            </div>
            <p className="idle-label">TAP TO ACTIVATE</p>
          </div>
        ) : (
          <div className="active-state">
            <div className="gif-frame">
              {!response ? (
                <img className="speakimg" src={speak} alt="Listening" />
              ) : (
                <img className="listeningimg" src={listening} alt="Responding" />
              )}
              <div className="gif-glow" />
            </div>
            <div className="status-bar">
              <span className="status-dot" />
              <span className="status-text">
                {!response ? "PROCESSING" : "RESPONDING"}
              </span>
            </div>
            <div className="prompt-card">
              <p className="prompt-text">{prompt}</p>
            </div>
          </div>
        )}
      </div>

      <div className="hud-corner bottom-left">
        <span>NEURAL</span><span>LINK</span>
      </div>
      <div className="hud-corner bottom-right">
        <span>GEN-AI</span><span>ACTIVE</span>
      </div>
    </div>
  );
}

export default App;