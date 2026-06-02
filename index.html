import React, { createContext, useState } from "react";
import run from "../gemini";

export const dataContext = createContext();

function UserContext({ children }) {
  let [speaking, setSpeaking] = useState(false);
  let [prompt, setPrompt] = useState("..listening");
  let [response, setResponse] = useState(false);

  function speak(text) {
    let utter = new SpeechSynthesisUtterance(text);
    utter.volume = 1;
    utter.pitch = 1;
    utter.rate = 1;
    utter.lang = "en-US";

    utter.onend = () => {
      setSpeaking(false); 
    };

    window.speechSynthesis.speak(utter);
  }

  async function aiResponse(prompt) {
    let text = await run(prompt);
    let newText = text
      .replace(/\*\*/g, "")
      .replace(/\*/g, "")
      .replace(/Google/g, "Alan Praful")
      .replace(/google/g, "Alan Praful");

    setPrompt(newText);
    speak(newText);
    setResponse(true);
  }

  const SpeechRecognition =
    window.SpeechRecognition || window.webkitSpeechRecognition;
  const recognition = new SpeechRecognition();

  recognition.onresult = (e) => {
    let currentIndex = e.resultIndex;
    let transcript = e.results[currentIndex][0].transcript;
    setPrompt(transcript);
    setCommand(transcript.toLowerCase());
  };

  function setCommand(command) {
    if (command.includes("open") && command.includes("youtube")) {
      window.open("https://www.youtube.com/");
      speak("Opening YouTube..");
      setPrompt("Opening YouTube");
    } else if (command.includes("time")) {
      let time = new Date().toLocaleString(undefined, {
        hour: "numeric",
        minute: "numeric",
      });
      speak(time);
    } else if (command.includes("date")) {
      let date = new Date().toLocaleString(undefined, {
        day: "numeric",
        month: "short",
      });
      speak(date);
    } else {
      aiResponse(command);
    }
  }

  let value = {
    recognition,
    speaking,
    setSpeaking,
    prompt,
    setPrompt,
    response,
    setResponse,
  };

  return (
    <dataContext.Provider value={value}>{children}</dataContext.Provider>
  );
}

export default UserContext;