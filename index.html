import React, { useState, useEffect, useRef, useLayoutEffect } from 'react';
import { 
  Apple, Wifi, Battery, Search, Command, Globe, Folder, 
  Terminal as TerminalIcon, Settings, Calculator as CalcIcon, StickyNote, 
  X, Minus, Maximize2, ChevronLeft, ChevronRight, RotateCw, 
  LayoutGrid, Moon, Sun, Image as ImageIcon, Cpu, Monitor, 
  Bluetooth, Volume2, Cast, Lock, LogOut, User, Disc,
  Mail, Music, Calendar as CalendarIcon, Code, FileText, Trash2, Play, 
  SkipForward, SkipBack, Pause, Inbox, Star, Send, Bell,
  MessageSquare, MoreHorizontal, Check, Type, Zap,
  Plus, XCircle, Layout, Laptop, Sparkles, Power, HardDrive, MemoryStick,
  Camera, RefreshCw, ArrowLeft, ArrowRight, FileJson, FileCode, Hash,
  MessageCircle, Video, Phone, Mic, Image as ImgIcon, Smartphone,
  BatteryMedium, BatteryCharging
} from 'lucide-react';

// --- Global Styles ---
const GlobalStyles = () => (
  <style>{`
    @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
    .animate-bounce-icon { animation: bounce 0.8s cubic-bezier(0.28, 0.84, 0.42, 1) infinite; }
    .macos-transition { transition: all 0.4s cubic-bezier(0.25, 0.1, 0.25, 1); }
    .window-transition { transition: width 0.4s cubic-bezier(0.25, 1, 0.5, 1), height 0.4s cubic-bezier(0.25, 1, 0.5, 1), left 0.4s cubic-bezier(0.25, 1, 0.5, 1), top 0.4s cubic-bezier(0.25, 1, 0.5, 1), transform 0.4s cubic-bezier(0.25, 1, 0.5, 1), opacity 0.3s ease; }
    .dock-icon-transition { transition: transform 0.2s cubic-bezier(0.25, 1, 0.5, 1), margin 0.2s; }
    
    /* Open Window Animation (Pop out) */
    @keyframes window-pop-in { 
      0% { transform: scale(0.9) translateY(20px); opacity: 0; filter: blur(10px); } 
      100% { transform: scale(1) translateY(0); opacity: 1; filter: blur(0); } 
    }
    .animate-open-window { 
      transform-origin: center center;
      animation: window-pop-in 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards; 
    }
    
    /* Dynamic Minimize Animation (Suck into specific Dock Icon) */
    @keyframes suck-into-dock {
      0% { 
        transform: translate(0, 0) scale(1); 
        opacity: 1; 
        filter: blur(0px);
        border-radius: inherit;
      }
      100% { 
        /* Variables calculated dynamically in JS */
        transform: translate(var(--min-tx, 0px), var(--min-ty, 50vh)) scale(var(--min-scale, 0.1)); 
        opacity: 0; 
        filter: blur(4px);
        border-radius: 50%;
      }
    }
    .animate-minimize-window { 
      transform-origin: center center;
      animation: suck-into-dock 0.5s cubic-bezier(0.32, 0.08, 0.24, 1) forwards; 
    }

    @keyframes shutter { 0% { opacity: 0; } 10% { opacity: 1; } 100% { opacity: 0; } }
    .animate-shutter { animation: shutter 0.2s ease-out; }
    
    /* Hide Scrollbar but keep functionality */
    .no-scrollbar::-webkit-scrollbar { display: none; }
    .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: rgba(150, 150, 150, 0.3); border-radius: 10px; }
    ::-webkit-scrollbar-thumb:hover { background: rgba(150, 150, 150, 0.5); }
  `}</style>
);

// --- Assets & Constants ---
const WALLPAPERS = {
  monterey: "https://images.unsplash.com/photo-1558591710-4b4a1ae0f04d?q=80&w=2560&auto=format&fit=crop",
  bigsur: "https://images.unsplash.com/photo-1622542796254-5b9c46a3d462?q=80&w=2560&auto=format&fit=crop",
  sonoma: "https://images.unsplash.com/photo-1506744038136-46273834b3fb?q=80&w=2560&auto=format&fit=crop"
};

const APPS = [
  { id: 'finder', name: 'Finder', icon: Folder, color: 'text-blue-500' },
  { id: 'safari', name: 'Safari', icon: Globe, color: 'text-blue-400' },
  { id: 'messages', name: 'Messages', icon: MessageCircle, color: 'text-green-500' },
  { id: 'calendar', name: 'Calendar', icon: CalendarIcon, color: 'text-red-500', isDynamic: true },
  { id: 'photos', name: 'Photos', icon: ImageIcon, color: 'text-pink-500' },
  { id: 'photobooth', name: 'Photo Booth', icon: Camera, color: 'text-green-500' },
  { id: 'mail', name: 'Mail', icon: Mail, color: 'text-blue-600' },
  { id: 'music', name: 'Music', icon: Music, color: 'text-red-500' },
  { id: 'vscode', name: 'VS Code', icon: Code, color: 'text-blue-400' },
  { id: 'terminal', name: 'Terminal', icon: TerminalIcon, color: 'text-gray-700' },
  { id: 'notes', name: 'Notes', icon: StickyNote, color: 'text-yellow-400' },
  { id: 'calculator', name: 'Calculator', icon: CalcIcon, color: 'text-orange-500' },
  { id: 'settings', name: 'Settings', icon: Settings, color: 'text-gray-500' },
];

const INITIAL_DESKTOP_ITEMS = [
  { id: 'hd', name: 'Macintosh HD', type: 'drive', x: 20, y: 20 },
  { id: 'readme', name: 'ReadMe.txt', type: 'file', x: 20, y: 110 },
];

// --- Data Structures ---
const MESSAGES = [
  { id: 1, name: 'Craig Federighi', avatar: 'CF', active: true, messages: [{ text: 'Hey, have you seen the new animations?', isMe: false }, { text: 'They look incredibly smooth!', isMe: true }, { text: 'That physics engine is neat.', isMe: false }] },
  { id: 2, name: 'Tim Cook', avatar: 'TC', active: false, messages: [{ text: 'Good morning!', isMe: false }, { text: 'Good morning Tim.', isMe: true }] },
  { id: 3, name: 'Jony Ive', avatar: 'JI', active: false, messages: [{ text: 'Aluminium.', isMe: false }] },
];

const FILE_SYSTEM = {
  'Recents': [ { name: 'Project_Alpha.pdf', type: 'PDF' }, { name: 'Vacation.jpg', type: 'Image' } ],
  'Desktop': [ { name: 'Screenshot_2024.png', type: 'Image' }, { name: 'Notes.txt', type: 'Text' } ],
  'Documents': [ { name: 'Resume.docx', type: 'Doc' }, { name: 'Budget.xlsx', type: 'Sheet' }, { name: 'Design_Spec.pdf', type: 'PDF' } ],
  'Downloads': [ { name: 'Installer.dmg', type: 'App' }, { name: 'Archive.zip', type: 'Zip' } ],
  'Applications': [ { name: 'Safari', type: 'App' }, { name: 'Mail', type: 'App' }, { name: 'Music', type: 'App' }, { name: 'VS Code', type: 'App' } ]
};

const EMAILS = [
  { id: 1, sender: 'Apple', subject: 'Welcome to macOS', time: '10:00 AM', content: 'Welcome to your new Mac. Experience the power of Liquid OS with our fluid animations and intuitive design.' },
  { id: 2, sender: 'Tim Cook', subject: 'Good Morning!', time: 'Yesterday', content: 'I hope you are enjoying the new update. We have put a lot of effort into making it seamless. \n\nBest,\nTim' },
  { id: 3, sender: 'GitHub', subject: 'Security Alert', time: 'Mon', content: 'A new sign-in was detected on your account. If this was you, you can ignore this email.' },
  { id: 4, sender: 'Dribbble', subject: 'Daily Inspiration', time: 'Sun', content: 'Check out the top designs of the day. Get inspired by the best creative work from around the world.' },
];

const CODE_FILES = {
  'App.js': `import React from 'react';\n\nfunction App() {\n  return (\n    <div className="app">\n      <h1>Hello World</h1>\n      <p>Welcome to VS Code</p>\n    </div>\n  );\n}\n\nexport default App;`,
  'index.css': `body {\n  margin: 0;\n  padding: 0;\n  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;\n  -webkit-font-smoothing: antialiased;\n}\n\n.app {\n  text-align: center;\n}`,
  'package.json': `{\n  "name": "macos-liquid",\n  "version": "1.0.0",\n  "private": true,\n  "dependencies": {\n    "react": "^18.2.0",\n    "react-dom": "^18.2.0",\n    "lucide-react": "^0.263.1"\n  }\n}`
};

// --- Utility Hooks ---
const useBattery = () => {
  const [level, setLevel] = useState(100);
  const [charging, setCharging] = useState(false);
  useEffect(() => {
    const interval = setInterval(() => {
      setLevel(l => (l > 10 ? l - 1 : 100)); 
      if (level < 20) setCharging(true); else setCharging(false);
    }, 60000); 
    return () => clearInterval(interval);
  }, [level]);
  return { level, charging };
};

// --- System App Components ---
const Spotlight = ({ isOpen, onClose, onOpenApp, isDark }) => {
  const [query, setQuery] = useState('');
  const inputRef = useRef(null);
  useEffect(() => { if (isOpen) { setQuery(''); setTimeout(() => inputRef.current?.focus(), 50); } }, [isOpen]);
  if (!isOpen) return null;
  const filteredApps = APPS.filter(app => app.name.toLowerCase().includes(query.toLowerCase()));
  let mathResult = null;
  try { if (/^[\d\s+\-*/().]+$/.test(query)) { const res = new Function('return ' + query)(); if (!isNaN(res) && query.trim().length > 0) mathResult = res; } } catch (e) {}
  return (
    <div className="absolute inset-0 z-[100] flex items-start justify-center pt-[20vh]" onClick={onClose}><div className={`w-[600px] rounded-2xl shadow-2xl backdrop-blur-2xl border transition-all duration-300 transform scale-100 opacity-100 animate-in fade-in zoom-in-95 ${isDark ? 'bg-gray-900/80 border-white/20 text-white' : 'bg-white/80 border-white/40 text-gray-900'}`} onClick={e => e.stopPropagation()}><div className="flex items-center p-4 gap-4"><Search size={24} className="opacity-50" /><input ref={inputRef} type="text" value={query} onChange={e => setQuery(e.target.value)} onKeyDown={e => {if(e.key==='Enter'){if(mathResult!==null)return;if(filteredApps.length){onOpenApp(filteredApps[0].id);onClose()}}} } placeholder="Spotlight Search" className="flex-1 bg-transparent border-none outline-none text-2xl font-light placeholder-opacity-30"/></div>{(query.length > 0) && (<div className={`border-t ${isDark ? 'border-white/10' : 'border-black/5'}`}>{mathResult !== null && (<div className="p-3 px-4 flex items-center gap-4 bg-blue-500/10 cursor-default"><div className="w-8 h-8 flex items-center justify-center"><CalcIcon size={20} /></div><div className="flex flex-col"><span className="text-sm font-semibold">Calculation</span><span className="text-xl font-bold">{mathResult}</span></div></div>)}{filteredApps.slice(0, 5).map((app, i) => (<div key={app.id} className={`p-3 px-4 flex items-center gap-4 cursor-pointer ${i === 0 ? (isDark ? 'bg-blue-600' : 'bg-blue-500 text-white') : (isDark ? 'hover:bg-white/10' : 'hover:bg-black/5')}`} onClick={() => { onOpenApp(app.id); onClose(); }}><div className="w-8 h-8 flex items-center justify-center"><app.icon size={20} className={i === 0 ? 'text-white' : app.color} /></div><div className="flex flex-col"><span className="text-sm font-medium">{app.name}</span><span className={`text-xs ${i === 0 ? 'opacity-80' : 'opacity-50'}`}>Application</span></div></div>))}</div>)}</div></div>
  );
};

const ControlCenter = ({ isDark, setIsDark, isOpen }) => {
  if (!isOpen) return null;
  return (<div className={`absolute top-10 right-2 w-80 p-3 rounded-2xl shadow-2xl backdrop-blur-3xl border animate-in fade-in zoom-in-95 duration-300 z-[90] ${isDark ? 'bg-gray-900/90 border-white/10 text-white' : 'bg-white/80 border-white/40 text-black'}`}><div className="grid grid-cols-2 gap-3 mb-3"><div className={`p-3 rounded-xl flex flex-col gap-3 border ${isDark ? 'bg-gray-800/50 border-white/5' : 'bg-white/50 border-black/5'}`}>{[{i: Wifi, l:'Wi-Fi'}, {i: Bluetooth, l:'Bluetooth'}, {i: Cast, l:'AirDrop'}].map((item, idx) => (<div key={idx} className="flex items-center gap-3"><div className="w-7 h-7 rounded-full bg-blue-500 text-white flex items-center justify-center shadow-lg shadow-blue-500/30"><item.i size={14} /></div><div className="flex flex-col leading-none"><span className="text-sm font-medium">{item.l}</span></div></div>))}</div><div className="grid grid-rows-2 gap-3"><div className={`p-3 rounded-xl flex items-center gap-3 border ${isDark ? 'bg-gray-800/50 border-white/5' : 'bg-white/50 border-black/5'}`}><div className={`w-8 h-8 rounded-full flex items-center justify-center ${isDark ? 'bg-gray-700' : 'bg-gray-200'}`}><Moon size={16} /></div><span className="text-xs font-medium">Focus</span></div><div className={`p-3 rounded-xl flex items-center gap-3 border ${isDark ? 'bg-gray-800/50 border-white/5' : 'bg-white/50 border-black/5'} cursor-pointer hover:opacity-80 transition-opacity`} onClick={() => setIsDark(!isDark)}><div className={`w-8 h-8 rounded-full flex items-center justify-center ${isDark ? 'bg-white text-black' : 'bg-gray-800 text-white'}`}><Disc size={16} /></div><span className="text-xs font-medium">{isDark ? 'Dark' : 'Light'} Mode</span></div></div></div><div className={`p-3 rounded-xl border mb-3 ${isDark ? 'bg-gray-800/50 border-white/5' : 'bg-white/50 border-black/5'}`}><div className="flex flex-col gap-3"><div className="flex items-center gap-2"><Sun size={14} className="opacity-50" /><div className="flex-1 h-6 bg-white/50 rounded-full border border-black/5 relative overflow-hidden cursor-pointer"><div className="absolute top-0 left-0 bottom-0 bg-white shadow-sm w-[70%]"></div></div></div><div className="flex items-center gap-2"><Volume2 size={14} className="opacity-50" /><div className="flex-1 h-6 bg-white/50 rounded-full border border-black/5 relative overflow-hidden cursor-pointer"><div className="absolute top-0 left-0 bottom-0 bg-white shadow-sm w-[50%]"></div></div></div></div></div></div>);
}

const AboutThisMac = () => (<div className="flex flex-col items-center p-8 gap-4 text-center h-full justify-center"><div className="w-24 h-24 rounded-full bg-gradient-to-br from-gray-200 to-gray-400 shadow-inner flex items-center justify-center mb-2"><Apple size={56} className="text-gray-600 drop-shadow-sm" /></div><div className="flex flex-col gap-1"><h2 className="text-2xl font-bold">macOS Liquid</h2><span className="text-xs font-medium opacity-60">Version 15.0 (Beta)</span></div><div className="flex flex-col gap-2 text-sm mt-4 w-full bg-black/5 dark:bg-white/10 p-4 rounded-xl"><div className="flex justify-between border-b border-black/10 dark:border-white/10 pb-2"><span className="opacity-60">Chip</span><span className="font-medium">Apple M3 Max</span></div><div className="flex justify-between border-b border-black/10 dark:border-white/10 pb-2"><span className="opacity-60">Memory</span><span className="font-medium">128 GB</span></div><div className="flex justify-between"><span className="opacity-60">Serial</span><span className="font-medium font-mono text-xs pt-0.5">X02LQD99</span></div></div><div className="flex gap-2 mt-2"><button className="px-3 py-1 bg-gray-200 dark:bg-gray-700 rounded text-xs hover:opacity-80">More Info...</button><button className="px-3 py-1 bg-gray-200 dark:bg-gray-700 rounded text-xs hover:opacity-80">Storage</button></div></div>);

// --- Content Apps (Collapsed for brevity, using same logic as before) ---
const SafariApp = ({ isDark }) => { const [history, setHistory] = useState(['apple']); const [historyIndex, setHistoryIndex] = useState(0); const pages = { apple: { title: 'Apple', icon: Apple, color: 'text-gray-500', url: 'apple.com' }, bing: { title: 'Bing', icon: Search, color: 'text-blue-500', url: 'bing.com' }, wiki: { title: 'Wikipedia', icon: Globe, color: 'text-gray-400', url: 'wikipedia.org' } }; const currentPageKey = history[historyIndex]; const currentPage = pages[currentPageKey]; const navigate = (pageKey) => { const newHistory = history.slice(0, historyIndex + 1); newHistory.push(pageKey); setHistory(newHistory); setHistoryIndex(newHistory.length - 1); }; const goBack = () => { if (historyIndex > 0) setHistoryIndex(historyIndex - 1); }; const goForward = () => { if (historyIndex < history.length - 1) setHistoryIndex(historyIndex + 1); }; const tabs = [{ id: 'apple', title: 'Apple', icon: Apple, color: 'text-gray-500' }, { id: 'bing', title: 'Bing', icon: Search, color: 'text-blue-500' }, { id: 'wiki', title: 'Wikipedia', icon: Globe, color: 'text-gray-400' }]; return (<div className={`flex flex-col h-full ${isDark ? 'bg-gray-800' : 'bg-gray-100'}`}><div className={`h-9 flex items-end px-2 gap-1 ${isDark ? 'bg-gray-900' : 'bg-gray-200'} pt-2`}>{tabs.map(tab => (<div key={tab.id} onClick={() => navigate(tab.id)} className={`flex-1 max-w-[200px] h-full rounded-t-lg flex items-center px-3 text-xs gap-2 cursor-pointer relative group ${currentPageKey === tab.id ? (isDark ? 'bg-gray-800 text-white' : 'bg-white text-gray-800 shadow-sm') : 'opacity-70 hover:opacity-100'}`}><tab.icon size={12} className={tab.color} /><span className="truncate flex-1">{tab.title}</span><X size={10} className="opacity-0 group-hover:opacity-50 hover:bg-gray-300 rounded" /></div>))}</div><div className={`h-12 flex items-center px-4 gap-4 border-b ${isDark ? 'bg-gray-800 border-gray-700 text-white' : 'bg-white border-gray-300 text-gray-800'}`}><div className="flex gap-4 opacity-80"><button onClick={goBack} disabled={historyIndex === 0} className="disabled:opacity-30 hover:text-blue-500"><ChevronLeft size={20} /></button><button onClick={goForward} disabled={historyIndex === history.length - 1} className="disabled:opacity-30 hover:text-blue-500"><ChevronRight size={20} /></button><RotateCw size={16} className="cursor-pointer hover:rotate-180 transition-transform duration-500" /></div><div className={`flex-1 h-8 rounded-lg flex items-center justify-center text-xs gap-2 relative group ${isDark ? 'bg-gray-900 hover:bg-gray-700' : 'bg-gray-100 hover:bg-gray-200 border border-transparent hover:border-gray-300'} transition-colors cursor-text`}><Lock size={10} className="opacity-50" /><span className="opacity-80 selection:bg-blue-300">{currentPage.url}</span></div></div><div className="flex-1 bg-white relative overflow-hidden">{currentPageKey === 'apple' && <div className="flex flex-col items-center justify-center h-full bg-black text-white animate-in fade-in duration-300"><Apple size={80} className="mb-6 animate-pulse" /><h1 className="text-4xl font-semibold mb-2">MacBook Pro</h1><p className="text-xl text-gray-400">Mind-blowing. Head-turning.</p><button onClick={() => navigate('bing')} className="mt-8 px-6 py-2 bg-blue-600 rounded-full hover:bg-blue-500 transition-colors">Buy Now</button></div>}{currentPageKey === 'bing' && <div className="flex flex-col items-center justify-center h-full bg-cover bg-center animate-in fade-in duration-300" style={{backgroundImage: 'url(https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?q=80&w=2000&auto=format&fit=crop)'}}><div className="bg-white/90 backdrop-blur p-8 rounded-xl shadow-2xl flex flex-col gap-4 w-96"><h2 className="text-2xl font-bold text-gray-800 flex items-center gap-2"><Globe className="text-blue-600"/> Bing</h2><input type="text" className="w-full border p-2 rounded shadow-inner" placeholder="Search..." onKeyDown={e => e.key === 'Enter' && navigate('wiki')} /><div className="text-xs text-gray-500 text-center">Try searching "Wiki"</div></div></div>}{currentPageKey === 'wiki' && <div className="p-8 h-full bg-white text-gray-900 overflow-y-auto animate-in fade-in duration-300"><h1 className="text-3xl font-serif font-bold border-b pb-4 mb-4">Wikipedia</h1><p className="font-serif leading-relaxed text-lg"><strong>macOS</strong> is a series of proprietary graphical operating systems developed and marketed by Apple Inc.</p><button onClick={() => navigate('apple')} className="mt-4 text-blue-600 hover:underline">Back to Apple</button></div>}</div></div>); };
const CalculatorApp = ({ isDark }) => { const [display, setDisplay] = useState('0'); const [prevVal, setPrevVal] = useState(null); const [operator, setOperator] = useState(null); const [waitingForNewVal, setWaitingForNewVal] = useState(false); const inputDigit = (digit) => { if (waitingForNewVal) { setDisplay(String(digit)); setWaitingForNewVal(false); } else { setDisplay(display === '0' ? String(digit) : display + digit); } }; const inputDot = () => { if (waitingForNewVal) { setDisplay('0.'); setWaitingForNewVal(false); } else if (display.indexOf('.') === -1) { setDisplay(display + '.'); } }; const clear = () => { setDisplay('0'); setPrevVal(null); setOperator(null); setWaitingForNewVal(false); }; const toggleSign = () => setDisplay(display.charAt(0) === '-' ? display.substring(1) : '-' + display); const inputPercent = () => setDisplay(String(parseFloat(display) / 100)); const performOperation = (nextOp) => { const inputValue = parseFloat(display); if (prevVal == null) { setPrevVal(inputValue); } else if (operator) { const currentVal = prevVal || 0; let newValue = inputValue; switch (operator) { case '+': newValue = currentVal + inputValue; break; case '-': newValue = currentVal - inputValue; break; case '×': newValue = currentVal * inputValue; break; case '÷': newValue = currentVal / inputValue; break; default: break; } setPrevVal(newValue); setDisplay(String(newValue)); } setWaitingForNewVal(true); setOperator(nextOp); }; const btnClass = "h-12 rounded-full font-medium text-lg flex items-center justify-center transition-all active:brightness-75"; return (<div className={`flex flex-col h-full ${isDark ? 'bg-gray-900/95 text-white' : 'bg-gray-800 text-white'} p-4`}><div className="flex-1 flex items-end justify-end text-5xl font-light mb-4 px-2 truncate overflow-hidden">{display}</div><div className="grid grid-cols-4 gap-3"><button onClick={clear} className={`${btnClass} bg-gray-500/80 hover:bg-gray-500`}>AC</button><button onClick={toggleSign} className={`${btnClass} bg-gray-500/80 hover:bg-gray-500`}>+/-</button><button onClick={inputPercent} className={`${btnClass} bg-gray-500/80 hover:bg-gray-500`}>%</button><button onClick={() => performOperation('÷')} className={`${btnClass} ${operator==='÷' && waitingForNewVal ? 'bg-orange-300 text-orange-600' : 'bg-orange-500 hover:bg-orange-400'}`}>÷</button>{[7, 8, 9].map(n => <button key={n} onClick={() => inputDigit(n)} className={`${btnClass} bg-gray-600/80 hover:bg-gray-600`}>{n}</button>)}<button onClick={() => performOperation('×')} className={`${btnClass} ${operator==='×' && waitingForNewVal ? 'bg-orange-300 text-orange-600' : 'bg-orange-500 hover:bg-orange-400'}`}>×</button>{[4, 5, 6].map(n => <button key={n} onClick={() => inputDigit(n)} className={`${btnClass} bg-gray-600/80 hover:bg-gray-600`}>{n}</button>)}<button onClick={() => performOperation('-')} className={`${btnClass} ${operator==='-' && waitingForNewVal ? 'bg-orange-300 text-orange-600' : 'bg-orange-500 hover:bg-orange-400'}`}>-</button>{[1, 2, 3].map(n => <button key={n} onClick={() => inputDigit(n)} className={`${btnClass} bg-gray-600/80 hover:bg-gray-600`}>{n}</button>)}<button onClick={() => performOperation('+')} className={`${btnClass} ${operator==='+' && waitingForNewVal ? 'bg-orange-300 text-orange-600' : 'bg-orange-500 hover:bg-orange-400'}`}>+</button><button onClick={() => inputDigit(0)} className={`${btnClass} bg-gray-600/80 hover:bg-gray-600 col-span-2 w-full justify-start pl-6`}>0</button><button onClick={inputDot} className={`${btnClass} bg-gray-600/80 hover:bg-gray-600`}>.</button><button onClick={() => performOperation('=')} className={`${btnClass} bg-orange-500 hover:bg-orange-400`}>=</button></div></div>); };
const PhotosApp = ({ isDark }) => { const [selectedImage, setSelectedImage] = useState(null); if (selectedImage) { return (<div className="absolute inset-0 bg-black/95 z-50 flex items-center justify-center animate-in fade-in duration-200"><button onClick={() => setSelectedImage(null)} className="absolute top-4 left-4 p-2 bg-white/10 hover:bg-white/20 text-white rounded-full transition-colors z-10 backdrop-blur-md"><ArrowLeft size={20}/></button><img src={selectedImage} className="w-full h-full object-contain" alt="Enlarged view" /></div>); } return (<div className={`h-full flex flex-col ${isDark ? 'bg-gray-900' : 'bg-white'}`}><div className={`p-4 border-b ${isDark ? 'border-gray-800 bg-gray-800/50' : 'border-gray-200 bg-gray-50/50'} flex justify-between items-center backdrop-blur`}><h3 className={`font-semibold text-lg ${isDark ? 'text-white' : 'text-black'}`}>Library</h3></div><div className="flex-1 overflow-y-auto p-4"><div className="grid grid-cols-3 gap-2">{[...Array(12)].map((_, i) => { const url = `https://picsum.photos/seed/${i+30}/500/500`; return (<div key={i} onClick={() => setSelectedImage(url)} className={`aspect-square rounded-lg overflow-hidden relative group cursor-pointer ${isDark ? 'bg-gray-800' : 'bg-gray-200'}`}><img src={url} className="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"/><div className="absolute inset-0 bg-black/0 group-hover:bg-black/20 transition-colors"/></div>); })}</div></div></div>); };
const MessagesApp = ({ isDark }) => { const [activeContactId, setActiveContactId] = useState(1); const activeChat = MESSAGES.find(m => m.id === activeContactId); return (<div className={`flex h-full ${isDark ? 'bg-gray-900 text-white' : 'bg-white text-gray-900'}`}><div className={`w-64 border-r ${isDark ? 'border-gray-800 bg-gray-800/50' : 'border-gray-200 bg-gray-50/50'} flex flex-col`}><div className="p-3 font-bold text-lg px-4 border-b border-transparent">Messages</div><div className="flex-1 overflow-y-auto px-2">{MESSAGES.map(contact => (<div key={contact.id} onClick={() => setActiveContactId(contact.id)} className={`flex items-center gap-3 p-2 rounded-lg cursor-pointer ${activeContactId === contact.id ? (isDark ? 'bg-blue-600' : 'bg-blue-500 text-white') : (isDark ? 'hover:bg-white/10' : 'hover:bg-black/5')}`}><div className={`w-10 h-10 rounded-full flex items-center justify-center font-bold ${activeContactId === contact.id ? 'bg-white/20 text-white' : 'bg-gray-400/20 text-gray-500'}`}>{contact.avatar}</div><div className="flex flex-col flex-1 overflow-hidden"><div className="flex justify-between items-baseline"><span className="font-semibold text-sm truncate">{contact.name}</span><span className={`text-[10px] ${activeContactId === contact.id ? 'opacity-80' : 'opacity-50'}`}>9:41 AM</span></div><span className={`text-xs truncate ${activeContactId === contact.id ? 'opacity-80' : 'opacity-60'}`}>{contact.messages[contact.messages.length-1].text}</span></div></div>))}</div></div><div className="flex-1 flex flex-col"><div className={`h-12 border-b ${isDark ? 'border-gray-800 bg-gray-900/50' : 'border-gray-200 bg-white/50'} flex items-center justify-between px-4 backdrop-blur-md z-10`}><div className="flex items-center gap-2"><span className="font-semibold text-sm">To: </span><span className="text-sm bg-blue-500/20 text-blue-500 px-2 py-0.5 rounded-full">{activeChat?.name}</span></div><div className="flex gap-4 text-blue-500"><Video size={20} className="cursor-pointer hover:opacity-70"/><Phone size={18} className="cursor-pointer hover:opacity-70"/></div></div><div className="flex-1 overflow-y-auto p-4 flex flex-col gap-2">{activeChat?.messages.map((msg, i) => (<div key={i} className={`max-w-[70%] px-4 py-2 rounded-2xl text-sm ${msg.isMe ? 'bg-blue-500 text-white self-end rounded-br-sm' : (isDark ? 'bg-gray-800 self-start rounded-bl-sm' : 'bg-gray-200 self-start rounded-bl-sm')}`}>{msg.text}</div>))}</div><div className={`p-4 ${isDark ? 'bg-gray-900' : 'bg-white'}`}><div className={`h-9 rounded-full border flex items-center px-4 gap-2 ${isDark ? 'border-gray-700 bg-gray-800' : 'border-gray-300 bg-white'}`}><Plus size={18} className="text-gray-400 cursor-pointer"/><input type="text" placeholder="iMessage" className="flex-1 bg-transparent outline-none text-sm"/><Mic size={16} className="text-gray-400 cursor-pointer"/></div></div></div></div>); };
const SettingsApp = ({ currentWallpaper, setWallpaper, isDark, setIsDark }) => { const [activeTab, setActiveTab] = useState('Appearance'); const menuItems = [{ name: 'Appearance', icon: Monitor }, { name: 'Wallpaper', icon: ImageIcon }, { name: 'Battery', icon: BatteryMedium }, { name: 'Wi-Fi', icon: Wifi }]; const renderContent = () => { switch (activeTab) { case 'Appearance': return (<div className="space-y-6 animate-in fade-in slide-in-from-right-4 duration-300"><h3 className="text-xl font-bold">Appearance</h3><div className={`p-4 rounded-xl border ${isDark ? 'bg-gray-800/50 border-white/10' : 'bg-white/50 border-black/5'}`}><div className="flex items-center justify-between"><span>Dark Mode</span><div onClick={() => setIsDark(!isDark)} className={`w-12 h-6 rounded-full p-1 transition-colors cursor-pointer ${isDark ? 'bg-green-500' : 'bg-gray-300'}`}><div className={`bg-white w-4 h-4 rounded-full shadow-md transform transition-transform ${isDark ? 'translate-x-6' : ''}`} /></div></div></div></div>); case 'Wallpaper': return (<div className="space-y-6 animate-in fade-in slide-in-from-right-4 duration-300"><h3 className="text-xl font-bold">Wallpaper</h3><div className="grid grid-cols-2 gap-4">{Object.entries(WALLPAPERS).map(([name, url]) => (<div key={name} onClick={() => setWallpaper(url)} className={`relative aspect-video rounded-xl overflow-hidden cursor-pointer border-4 transition-all ${currentWallpaper === url ? 'border-blue-500' : 'border-transparent hover:scale-105'}`}><img src={url} className="w-full h-full object-cover" /><div className="absolute bottom-0 left-0 right-0 bg-black/50 text-white text-xs py-1 text-center capitalize backdrop-blur-sm">{name}</div></div>))}</div></div>); default: return (<div className="flex flex-col items-center justify-center h-64 opacity-50"><Settings size={48} className="mb-4" /><p>Settings for {activeTab} not implemented in demo.</p></div>); } }; return (<div className={`flex h-full ${isDark ? 'bg-gray-900 text-white' : 'bg-gray-100 text-gray-900'}`}><div className={`w-56 p-4 flex flex-col gap-1 border-r ${isDark ? 'border-gray-800' : 'border-gray-200'}`}><div className="flex items-center gap-2 px-2 py-3 mb-2"><div className="w-8 h-8 rounded-full bg-gray-400/30 flex items-center justify-center"><User size={16}/></div><div className="flex flex-col leading-none"><span className="text-sm font-bold">Guest User</span><span className="text-[10px] opacity-60">Apple ID</span></div></div>{menuItems.map(item => (<div key={item.name} onClick={() => setActiveTab(item.name)} className={`flex items-center gap-3 px-3 py-1.5 rounded-lg cursor-pointer text-sm ${activeTab === item.name ? (isDark ? 'bg-blue-600 text-white' : 'bg-blue-500 text-white') : (isDark ? 'hover:bg-white/10' : 'hover:bg-black/5')}`}><item.icon size={16} /><span>{item.name}</span></div>))}</div><div className="flex-1 p-8 overflow-y-auto">{renderContent()}</div></div>); };
const FinderApp = ({ isDark }) => { const [currentPath, setCurrentPath] = useState('Recents'); const sidebarItems = Object.keys(FILE_SYSTEM); return (<div className="flex h-full text-sm"><div className={`w-40 p-3 flex flex-col gap-1 ${isDark ? 'bg-gray-800/50 text-gray-300' : 'bg-gray-100/50 text-gray-600'} backdrop-blur-md`}><div className="text-xs font-bold text-gray-400 px-2 mb-1">Favorites</div>{sidebarItems.map(item => (<div key={item} onClick={() => setCurrentPath(item)} className={`px-2 py-1 rounded cursor-pointer flex items-center gap-2 ${currentPath === item ? (isDark ? 'bg-white/20' : 'bg-gray-300/50') : (isDark ? 'hover:bg-white/10' : 'hover:bg-black/5')}`}>{item === 'Applications' ? <LayoutGrid size={14}/> : <Folder size={14}/>} {item}</div>))}</div><div className={`flex-1 flex flex-col ${isDark ? 'text-white' : 'text-gray-900'}`}><div className={`h-10 flex items-center px-4 border-b ${isDark ? 'border-white/10' : 'border-black/5'}`}><div className="flex gap-4 opacity-50"><ChevronLeft size={18}/><ChevronRight size={18}/></div><span className="ml-4 font-semibold">{currentPath}</span></div><div className="p-4 grid grid-cols-4 gap-4 overflow-auto content-start flex-1">{FILE_SYSTEM[currentPath]?.map((file, i) => (<div key={i} className={`flex flex-col items-center gap-2 p-2 rounded cursor-pointer ${isDark ? 'hover:bg-white/10' : 'hover:bg-blue-100/50'}`}>{file.type === 'App' ? <LayoutGrid size={40} className="text-purple-400"/> : file.type === 'PDF' ? <FileText size={40} className="text-red-400"/> : file.type === 'Image' ? <ImageIcon size={40} className="text-blue-400"/> : <Folder size={40} className="text-blue-400 fill-current" />}<span className="text-center truncate w-full">{file.name}</span></div>))}</div></div></div>); };
const MailApp = ({ isDark }) => { const [selectedMailId, setSelectedMailId] = useState(1); const selectedMail = EMAILS.find(e => e.id === selectedMailId); return (<div className="flex h-full"><div className={`w-48 border-r ${isDark ? 'border-gray-700 bg-gray-800/50' : 'border-gray-200 bg-gray-50/50'} flex flex-col`}><div className="p-3 font-semibold text-sm opacity-50">Mailboxes</div><div className={`px-3 py-1 mx-2 rounded-md flex items-center gap-2 text-sm ${isDark?'bg-blue-600':'bg-blue-500'} text-white`}><Inbox size={14}/> Inbox</div><div className="px-3 py-1 mx-2 rounded-md flex items-center gap-2 text-sm opacity-70"><Send size={14}/> Sent</div><div className="px-3 py-1 mx-2 rounded-md flex items-center gap-2 text-sm opacity-70"><Trash2 size={14}/> Trash</div></div><div className={`w-64 border-r ${isDark ? 'border-gray-700 bg-gray-900/50' : 'border-gray-200 bg-white/50'} flex flex-col overflow-y-auto`}>{EMAILS.map(email => (<div key={email.id} onClick={() => setSelectedMailId(email.id)} className={`p-3 border-b cursor-pointer ${selectedMailId === email.id ? (isDark ? 'bg-blue-600/20' : 'bg-blue-100') : (isDark ? 'border-gray-800 hover:bg-white/5' : 'border-gray-100 hover:bg-gray-50')}`}><div className="flex justify-between items-baseline mb-1"><span className="font-semibold text-sm">{email.sender}</span><span className="text-[10px] opacity-50">{email.time}</span></div><div className="text-xs font-medium mb-1">{email.subject}</div><div className="text-[10px] opacity-60 line-clamp-2">{email.content}</div></div>))}</div><div className={`flex-1 p-8 flex flex-col ${isDark ? 'text-white' : 'text-gray-800'}`}>{selectedMail ? (<><div className="flex justify-between items-center mb-6 border-b pb-4 dark:border-gray-700"><div><h2 className="text-xl font-bold">{selectedMail.subject}</h2><div className="text-sm opacity-70 mt-1">From: {selectedMail.sender}</div></div><div className="text-xs opacity-50">{selectedMail.time}</div></div><div className="leading-relaxed whitespace-pre-wrap">{selectedMail.content}</div></>) : (<div className="flex-1 flex flex-col items-center justify-center opacity-50"><Mail size={48} className="mb-4"/><p>No Message Selected</p></div>)}</div></div>); };
const MusicApp = ({ isDark }) => { const [isPlaying, setIsPlaying] = useState(false); return (<div className={`h-full flex flex-col ${isDark ? 'bg-gradient-to-br from-gray-900 to-black text-white' : 'bg-gradient-to-br from-gray-100 to-white text-gray-900'}`}><div className="flex-1 flex items-center justify-center p-6 relative overflow-hidden"><img src="https://images.unsplash.com/photo-1493225255756-d9584f8606e9?q=80&w=600&auto=format&fit=crop" className="absolute inset-0 w-full h-full object-cover opacity-20 blur-2xl scale-150 pointer-events-none" /><div className={`w-56 h-56 rounded-xl shadow-2xl bg-gray-300 overflow-hidden relative group transition-transform duration-700 ${isPlaying ? 'scale-105' : 'scale-100'}`}><img src="https://images.unsplash.com/photo-1493225255756-d9584f8606e9?q=80&w=600&auto=format&fit=crop" className="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"/></div></div><div className="h-36 bg-white/10 backdrop-blur-md p-6 flex flex-col justify-between"><div className="text-center"><div className="font-bold text-lg">Liquid Vibes</div><div className="text-sm opacity-60">Unknown Artist</div></div><div className="w-full bg-gray-400/30 h-1 rounded-full overflow-hidden mt-4"><div className={`h-full bg-red-500 ${isPlaying ? 'w-2/3' : 'w-1/3'} transition-all duration-[2000ms] ease-linear`}></div></div><div className="flex justify-center items-center gap-8 mt-2"><SkipBack size={24} className="opacity-70 hover:opacity-100 cursor-pointer"/><div onClick={() => setIsPlaying(!isPlaying)} className="w-12 h-12 rounded-full bg-red-500 text-white flex items-center justify-center shadow-lg hover:scale-105 transition-transform cursor-pointer">{isPlaying ? <Pause size={20} fill="currentColor" /> : <Play size={20} fill="currentColor" className="ml-1"/>}</div><SkipForward size={24} className="opacity-70 hover:opacity-100 cursor-pointer"/></div></div></div>); };
const PhotoBoothApp = () => { const [flash, setFlash] = useState(false); const takePhoto = () => { setFlash(true); setTimeout(() => setFlash(false), 200); }; return (<div className="h-full bg-gray-900 flex flex-col relative overflow-hidden">{flash && <div className="absolute inset-0 bg-white z-50 animate-shutter pointer-events-none"></div>}<div className="flex-1 bg-black flex items-center justify-center relative"><div className="w-full h-full bg-gray-800 flex items-center justify-center text-gray-600"><User size={120} className="opacity-20" /><div className="absolute bottom-4 right-4 text-white/50 text-xs font-mono">REC ●</div></div></div><div className="h-20 bg-gray-100 border-t flex items-center justify-center gap-8"><div className="w-12 h-12 bg-gray-300 rounded-lg"></div><button onClick={takePhoto} className="w-14 h-14 rounded-full bg-red-500 border-4 border-white shadow-lg active:scale-95 transition-transform"></button><button className="w-12 h-12 flex items-center justify-center text-gray-500 hover:bg-gray-200 rounded-lg"><RefreshCw size={24}/></button></div></div>); };
const VSCodeApp = () => { const [activeFile, setActiveFile] = useState('App.js'); return (<div className="h-full bg-[#1e1e1e] text-[#d4d4d4] flex font-mono text-sm"><div className="w-12 bg-[#333333] flex flex-col items-center py-4 gap-4"><Folder size={24} className="text-white"/><Search size={24} /><Settings size={24} className="mt-auto"/></div><div className="w-48 bg-[#252526] flex flex-col"><div className="p-2 text-xs font-bold uppercase tracking-wider pl-4">Explorer</div>{Object.keys(CODE_FILES).map(fileName => (<div key={fileName} onClick={() => setActiveFile(fileName)} className={`px-4 py-1 cursor-pointer flex items-center gap-2 ${activeFile === fileName ? 'bg-[#37373d] text-white' : 'hover:bg-[#2a2d2e]'}`}>{fileName.endsWith('.js') ? <FileCode size={14} className="text-yellow-400"/> : fileName.endsWith('.css') ? <Hash size={14} className="text-blue-300"/> : <FileJson size={14} className="text-red-400"/>}{fileName}</div>))}</div><div className="flex-1 flex flex-col"><div className="h-9 bg-[#1e1e1e] flex items-center px-4 border-b border-black/20"><span className="text-sm">{activeFile}</span></div><div className="flex-1 p-4 overflow-auto bg-[#1e1e1e]"><pre className="font-mono text-sm leading-relaxed text-[#9cdcfe]">{CODE_FILES[activeFile]}</pre></div></div></div>); };
const CalendarApp = ({ isDark }) => { const today = new Date().getDate(); return (<div className={`h-full flex flex-col ${isDark ? 'bg-gray-900 text-white' : 'bg-white text-gray-900'}`}><div className="p-4 border-b border-gray-200 dark:border-gray-800 flex justify-between"><h2 className="text-xl font-bold text-red-500">October <span className="text-gray-500 font-normal">2024</span></h2></div><div className="flex-1 p-4 grid grid-cols-7 gap-1 content-start">{['S','M','T','W','T','F','S'].map((d, i)=><div key={i} className="text-center text-xs opacity-50 mb-2">{d}</div>)}{[...Array(35)].map((_,i)=><div key={i} className="aspect-square flex justify-center pt-1 border-t border-gray-100 dark:border-gray-800">{i-2>0 && i-2<=31 && <span className={`w-6 h-6 rounded-full flex items-center justify-center text-sm ${i-2===today?'bg-red-500 text-white font-bold':''}`}>{i-2}</span>}</div>)}</div></div>); };
const InteractiveTerminal = () => { const [history, setHistory] = useState(['Last login: ' + new Date().toString().split(' GMT')[0], 'Type "help" for commands.']); const [input, setInput] = useState(''); const endRef = useRef(null); const handleKeyDown = (e) => { if (e.key === 'Enter') { const cmd = input.trim(); const newHistory = [...history, `guest@mac:~$ ${input}`]; switch (cmd.toLowerCase()) { case 'help': newHistory.push('Available commands: help, clear, date, whoami, ls, neofetch, echo [text]'); break; case 'clear': setHistory([]); setInput(''); return; case 'date': newHistory.push(new Date().toString()); break; case 'whoami': newHistory.push('guest_user'); break; case 'ls': newHistory.push('Desktop  Documents  Downloads  Music  Pictures'); break; case 'neofetch': newHistory.push(`       .:'\n    _ :'_    OS: macOS Liquid\n  .' \`_.'    Host: MacBook Pro\n : .:\`      Kernel: 24.0.0\n : :        Uptime: 2 mins\n : :        Packages: 1 (npm)\n  '-      Shell: zsh 5.9\n             Resolution: 3024x1964\n             DE: Aqua\n             WM: Quartz Compositor\n             Theme: Liquid Dark [GTK2/3]\n             Icons: SF Symbols`); break; default: if (cmd.startsWith('echo ')) newHistory.push(cmd.substring(5)); else if (cmd !== '') newHistory.push(`zsh: command not found: ${cmd}`); } setHistory(newHistory); setInput(''); } }; useEffect(() => { endRef.current?.scrollIntoView({ behavior: 'smooth' }); }, [history]); return (<div className="h-full bg-[#1c1c1c]/95 text-green-400 font-mono p-4 text-sm overflow-y-auto" onClick={() => document.getElementById('term-input')?.focus()}>{history.map((line, i) => <div key={i} className="whitespace-pre-wrap mb-1 leading-tight">{line}</div>)}<div className="flex gap-2"><span className="text-blue-400">guest@mac:~$</span><input id="term-input" type="text" value={input} onChange={e => setInput(e.target.value)} onKeyDown={handleKeyDown} className="bg-transparent border-none outline-none text-green-400 flex-1 caret-green-400" autoFocus autoComplete="off" /></div><div ref={endRef} /></div>); };
const CalendarIconDynamic = () => { const date = new Date(); return (<div className="w-full h-full bg-white rounded-xl shadow-sm overflow-hidden flex flex-col relative pointer-events-none"><div className="h-[25%] bg-red-500 flex items-center justify-center"><span className="text-white font-bold text-[8px] tracking-wide mt-[1px]">{date.toLocaleDateString('en-US', { weekday: 'short' }).toUpperCase()}</span></div><div className="flex-1 flex items-center justify-center"><span className="text-gray-800 font-medium text-xl leading-none -mt-1">{date.getDate()}</span></div></div>); };

// --- Window Component ---
const Window = ({ window, onClose, onMinimize, onMaximize, onFocus, updatePosition, isDark, setWallpaper, setIsDark, wallpaper, notesContent, setNotesContent }) => {
  const nodeRef = useRef(null);
  const [isDragging, setIsDragging] = useState(false);
  const [dragOffset, setDragOffset] = useState({ x: 0, y: 0 });
  const [isMinimizing, setIsMinimizing] = useState(false);

  const handleMouseDown = (e) => {
    e.stopPropagation();
    if (window.isMaximized) return;
    onFocus(window.id);
    setIsDragging(true);
    const rect = nodeRef.current.getBoundingClientRect();
    setDragOffset({ x: e.clientX - rect.left, y: e.clientY - rect.top });
  };

  useEffect(() => {
    const handleMouseMove = (e) => {
      if (isDragging) {
        let newX = e.clientX - dragOffset.x;
        let newY = e.clientY - dragOffset.y;
        const snapThreshold = 20;
        if (newX < snapThreshold) newX = 0;
        if (newY < 32 + snapThreshold) newY = 32; 
        newY = Math.max(32, newY);
        updatePosition(window.id, newX, newY);
      }
    };
    const handleMouseUp = () => setIsDragging(false);
    if (isDragging) { document.addEventListener('mousemove', handleMouseMove); document.addEventListener('mouseup', handleMouseUp); }
    return () => { document.removeEventListener('mousemove', handleMouseMove); document.removeEventListener('mouseup', handleMouseUp); };
  }, [isDragging, dragOffset, window.id, updatePosition]);

  // Magical Scale/Genie Effect Logic
  const handleMinimize = (e) => {
    e.stopPropagation();
    const dockIcon = document.getElementById(`dock-icon-${window.appId}`);
    if (dockIcon && nodeRef.current) {
      const iconRect = dockIcon.getBoundingClientRect();
      const winRect = nodeRef.current.getBoundingClientRect();
      
      const winCenterX = winRect.left + winRect.width / 2;
      const winCenterY = winRect.top + winRect.height / 2;
      const iconCenterX = iconRect.left + iconRect.width / 2;
      const iconCenterY = iconRect.top + iconRect.height / 2;

      const tx = iconCenterX - winCenterX;
      const ty = iconCenterY - winCenterY;
      const scale = Math.max(iconRect.width / winRect.width, 0.05);

      nodeRef.current.style.setProperty('--min-tx', `${tx}px`);
      nodeRef.current.style.setProperty('--min-ty', `${ty}px`);
      nodeRef.current.style.setProperty('--min-scale', scale);
    }

    setIsMinimizing(true);
    // Wait for CSS animation to finish before removing from layout
    setTimeout(() => {
      onMinimize(window.id);
      setIsMinimizing(false);
    }, 450); 
  };

  if (window.minimized && !isMinimizing) return null;
  
  const style = window.isMaximized ? { left: 0, top: 32, width: '100%', height: 'calc(100% - 32px)', borderRadius: 0 } : { left: window.x, top: window.y, width: window.width, height: window.height };
  const baseGlass = isDark ? 'bg-gray-900/90 border-white/10' : 'bg-white/85 border-white/40';
  
  // Apply either open animation, minimize animation, or standard transition
  const animationClass = isMinimizing ? 'animate-minimize-window' : 'animate-open-window';

  return (
    <div ref={nodeRef} style={{...style, zIndex: window.zIndex}} className={`absolute flex flex-col backdrop-blur-2xl border shadow-2xl ${!window.isMaximized && 'rounded-xl'} ${baseGlass} overflow-hidden window-transition ${animationClass}`} onMouseDown={handleMouseDown} onClick={(e) => e.stopPropagation()}>
      <div className={`h-9 flex items-center px-4 select-none border-b ${isDark ? 'border-white/5' : 'border-black/5'}`} onDoubleClick={(e) => {e.stopPropagation(); onMaximize(window.id);}}>
        <div className="flex gap-2 group"><button onClick={(e)=>{e.stopPropagation();onClose(window.id)}} className="w-3 h-3 rounded-full bg-[#FF5F57] group-hover:brightness-90 flex items-center justify-center text-[8px] text-black/50 opacity-0 group-hover:opacity-100"><X size={8} strokeWidth={4}/></button><button onClick={handleMinimize} className="w-3 h-3 rounded-full bg-[#FEBC2E] group-hover:brightness-90 flex items-center justify-center text-[8px] text-black/50 opacity-0 group-hover:opacity-100"><Minus size={8} strokeWidth={4}/></button><button onClick={(e)=>{e.stopPropagation();onMaximize(window.id)}} className="w-3 h-3 rounded-full bg-[#28C840] group-hover:brightness-90 flex items-center justify-center text-[8px] text-black/50 opacity-0 group-hover:opacity-100"><Maximize2 size={6} strokeWidth={4}/></button></div>
        <div className={`flex-1 text-center text-sm font-medium opacity-80 ${isDark ? 'text-gray-200' : 'text-gray-800'}`}>{window.appId === 'about' ? 'System Information' : APPS.find(a => a.id === window.appId)?.name}</div>
        <div className="w-14"/>
      </div>
      <div className="flex-1 overflow-auto relative cursor-default no-scrollbar">
         {window.appId === 'terminal' ? <InteractiveTerminal /> : 
          window.appId === 'calculator' ? <CalculatorApp isDark={isDark} /> :
          window.appId === 'about' ? <AboutThisMac /> :
          window.appId === 'notes' ? <textarea value={notesContent} onChange={(e) => setNotesContent(e.target.value)} className={`w-full h-full bg-transparent p-4 resize-none outline-none font-serif text-lg ${isDark?'text-white':'text-gray-800'}`} placeholder="Write something..." /> :
          window.appId === 'safari' ? <SafariApp isDark={isDark} /> :
          window.appId === 'photobooth' ? <PhotoBoothApp /> :
          window.appId === 'calendar' ? <CalendarApp isDark={isDark} /> :
          window.appId === 'mail' ? <MailApp isDark={isDark} /> :
          window.appId === 'music' ? <MusicApp isDark={isDark} /> :
          window.appId === 'photos' ? <PhotosApp isDark={isDark} /> :
          window.appId === 'messages' ? <MessagesApp isDark={isDark} /> :
          window.appId === 'vscode' ? <VSCodeApp /> :
          window.appId === 'finder' ? <FinderApp isDark={isDark} /> :
          window.appId === 'settings' ? <SettingsApp currentWallpaper={wallpaper} setWallpaper={setWallpaper} isDark={isDark} setIsDark={setIsDark} /> :
          <div className="flex flex-col items-center justify-center h-full opacity-40"><span className="text-4xl mb-4">✨</span><p>App Content</p></div>}
      </div>
    </div>
  );
};

// --- Desktop Icon ---
const DesktopIcon = ({ item, isSelected, onSelect, onPositionChange }) => {
  const [isDragging, setIsDragging] = useState(false);
  const [dragOffset, setDragOffset] = useState({ x: 0, y: 0 });
  const iconRef = useRef(null);
  const handleMouseDown = (e) => { e.stopPropagation(); onSelect(item.id); setIsDragging(true); const rect = iconRef.current.getBoundingClientRect(); setDragOffset({ x: e.clientX - item.x, y: e.clientY - item.y }); };
  useEffect(() => { const hM = (e) => { if (isDragging) onPositionChange(item.id, e.clientX - dragOffset.x, e.clientY - dragOffset.y); }; const hU = () => setIsDragging(false); if (isDragging) { document.addEventListener('mousemove', hM); document.addEventListener('mouseup', hU); } return () => { document.removeEventListener('mousemove', hM); document.removeEventListener('mouseup', hU); }; }, [isDragging, dragOffset, item.id, onPositionChange]);
  return <div ref={iconRef} style={{ left: item.x, top: item.y }} className={`absolute w-20 flex flex-col items-center gap-1 p-2 rounded-lg macos-transition border ${isSelected ? 'bg-white/20 border-white/30 backdrop-blur-sm' : 'border-transparent hover:bg-white/10'}`} onMouseDown={handleMouseDown} onDoubleClick={() => alert(`Opened ${item.name}`)}><div className="w-12 h-12 flex items-center justify-center drop-shadow-2xl">{item.type==='drive'?<HardDrive size={44} className="text-gray-300 fill-gray-500/50"/>:<FileText size={40} className="text-white"/>}</div><span className={`text-xs text-center font-medium leading-tight px-1 rounded ${isSelected?'text-white':'text-white shadow-black drop-shadow-md'}`}>{item.name}</span></div>;
};

// --- Dock Context Menu ---
const DockMenu = ({ x, y, appId, onClose, onQuit, onOpen, isDark }) => (
  <div className={`absolute z-[100] w-40 rounded-xl shadow-2xl backdrop-blur-xl border py-1 flex flex-col text-sm animate-in fade-in zoom-in-95 duration-100 ${isDark ? 'bg-gray-800/90 border-gray-600 text-white' : 'bg-white/90 border-white/40 text-gray-800'}`} style={{ left: x, top: y - 100 }} onClick={e => e.stopPropagation()}>
    <div className="px-3 py-1.5 opacity-50 text-xs border-b border-gray-500/20 mb-1">{APPS.find(a=>a.id===appId)?.name}</div>
    <button onClick={onOpen} className="text-left px-3 py-1.5 hover:bg-blue-500 hover:text-white transition-colors">Open</button>
    <div className={`h-px my-1 mx-2 ${isDark ? 'bg-gray-600' : 'bg-gray-300'}`} />
    <button onClick={onQuit} className="text-left px-3 py-1.5 hover:bg-blue-500 hover:text-white transition-colors">Quit</button>
  </div>
);

// --- Lock Screen ---
const LockScreen = ({ wallpaper, onUnlock, isDark }) => {
  const [password, setPassword] = useState('');
  const time = new Date();
  return (
    <div className="absolute inset-0 z-[200] bg-cover bg-center flex flex-col items-center justify-center text-white" style={{ backgroundImage: `url(${wallpaper})` }}><div className="absolute inset-0 bg-black/40 backdrop-blur-xl"></div><div className="z-10 flex flex-col items-center mb-16 animate-in fade-in slide-in-from-top-4 duration-700"><div className="text-6xl font-thin tracking-tight">{time.toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'})}</div><div className="text-lg font-medium opacity-80 mt-2">{time.toLocaleDateString([], {weekday: 'long', month: 'long', day: 'numeric'})}</div></div><div className="z-10 flex flex-col items-center gap-4 animate-in fade-in zoom-in duration-500"><div className="w-20 h-20 rounded-full bg-gray-200/20 backdrop-blur-md shadow-2xl flex items-center justify-center ring-1 ring-white/30"><User size={40} className="text-white/90" /></div><div className="text-xl font-semibold drop-shadow-md">Guest User</div><div className="flex gap-2"><input type="password" value={password} onChange={e => setPassword(e.target.value)} onKeyDown={e => e.key === 'Enter' && onUnlock()} placeholder="Enter Password" className="px-4 py-1.5 rounded-full bg-white/20 border border-white/20 text-white placeholder-white/50 text-sm focus:outline-none focus:bg-white/30 transition-all w-40 text-center backdrop-blur-md shadow-inner" autoFocus /><button onClick={onUnlock} className="w-8 h-8 rounded-full bg-white/20 flex items-center justify-center hover:bg-white/40 transition-colors"><ArrowRight size={14}/></button></div></div><div className="absolute bottom-10 flex flex-col items-center gap-2 opacity-60"><div className="text-xs">Press Enter to Unlock</div></div></div>
  );
};

// --- Custom Battery Icon ---
const DynamicBatteryIcon = ({ level, isCharging, isDark }) => {
  return (
    <div className="flex items-center gap-1.5">
      <span className="text-xs font-medium">{level}%</span>
      <div className={`relative flex items-center justify-start w-6 h-[11px] border rounded-[3px] p-[1px] ${isDark ? 'border-white/50' : 'border-black/50'}`}>
        <div className={`absolute -right-[3px] w-[2px] h-1.5 rounded-r-[1px] ${isDark ? 'bg-white/50' : 'bg-black/50'}`}></div>
        <div 
          className={`h-full rounded-[1.5px] transition-all duration-500 ${level <= 20 ? 'bg-red-500' : (isDark ? 'bg-white' : 'bg-black')} ${isCharging ? 'opacity-50' : 'opacity-100'}`} 
          style={{ width: `${level}%` }}
        ></div>
        {isCharging && (
          <div className="absolute inset-0 flex items-center justify-center">
            <Zap size={10} className={`${isDark ? 'text-black' : 'text-white'} fill-current stroke-none drop-shadow-md`} />
          </div>
        )}
      </div>
    </div>
  );
};

// --- Main App ---
export default function App() {
  const [wallpaper, setWallpaper] = useState(WALLPAPERS.monterey);
  const [isDark, setIsDark] = useState(false);
  const [windows, setWindows] = useState([]);
  const [desktopItems, setDesktopItems] = useState(INITIAL_DESKTOP_ITEMS);
  const [selectedItemIds, setSelectedItemIds] = useState([]);
  const [activeWindowId, setActiveWindowId] = useState(null);
  const [maxZIndex, setMaxZIndex] = useState(10);
  const [currentTime, setCurrentTime] = useState(new Date());
  const [isLaunchpadOpen, setIsLaunchpadOpen] = useState(false);
  const [dockHoverIndex, setDockHoverIndex] = useState(null);
  const [isControlCenterOpen, setIsControlCenterOpen] = useState(false);
  const [isSpotlightOpen, setIsSpotlightOpen] = useState(false);
  const [bouncingAppId, setBouncingAppId] = useState(null);
  const [dockMenu, setDockMenu] = useState(null); 
  const [contextMenu, setContextMenu] = useState(null);
  const [notesContent, setNotesContent] = useState(''); // Persistent Notes
  const [isLocked, setIsLocked] = useState(true); // Lock Screen State
  const { level: batteryLevel, charging: isCharging } = useBattery();

  useEffect(() => { const i = setInterval(() => setCurrentTime(new Date()), 1000); return () => clearInterval(i); }, []);

  // --- Window Management ---
  const openApp = (appId) => {
    setIsLaunchpadOpen(false);
    setDockMenu(null);
    setBouncingAppId(appId);
    setTimeout(() => setBouncingAppId(null), 1600);

    const existing = windows.find(w => w.appId === appId);
    if (existing) {
      if (existing.minimized) {
        setWindows(prev => prev.map(w => w.id === existing.id ? { ...w, minimized: false, zIndex: maxZIndex + 1 } : w));
        setMaxZIndex(prev => prev + 1);
        setActiveWindowId(existing.id);
      } else focusWindow(existing.id);
    } else {
      setTimeout(() => {
        const isSmall = ['calculator', 'music', 'calendar', 'about', 'photobooth', 'messages'].includes(appId);
        const newWin = { id: Date.now(), appId, x: 100 + windows.length*30, y: 100 + windows.length*30, width: isSmall ? 350 : 800, height: isSmall ? 480 : 600, zIndex: maxZIndex + 1, minimized: false, isMaximized: false };
        setWindows(prev => [...prev, newWin]);
        setMaxZIndex(prev => prev + 1);
        setActiveWindowId(newWin.id);
      }, 300);
    }
  };

  const closeWindow = (id) => setWindows(prev => prev.filter(w => w.id !== id));
  const quitApp = (appId) => { setWindows(prev => prev.filter(w => w.appId !== appId)); setDockMenu(null); };
  const minimizeWindow = (id) => { setWindows(prev => prev.map(w => w.id === id ? { ...w, minimized: true } : w)); setActiveWindowId(null); };
  const maximizeWindow = (id) => { setWindows(prev => prev.map(w => w.id === id ? { ...w, isMaximized: !w.isMaximized, zIndex: maxZIndex + 1 } : w)); setMaxZIndex(prev => prev + 1); setActiveWindowId(id); };
  const focusWindow = (id) => { if (activeWindowId !== id) { setWindows(prev => prev.map(w => w.id === id ? { ...w, zIndex: maxZIndex + 1 } : w)); setMaxZIndex(prev => prev + 1); setActiveWindowId(id); } };
  const updateWindowPos = (id, x, y) => setWindows(prev => prev.map(w => w.id === id ? { ...w, x, y } : w));
  const updateItemPos = (id, x, y) => setDesktopItems(prev => prev.map(item => item.id === id ? { ...item, x, y } : item));

  // --- Interaction Handlers ---
  const handleBackgroundClick = () => {
    setIsControlCenterOpen(false); setIsSpotlightOpen(false); setSelectedItemIds([]); setActiveWindowId(null); setIsLaunchpadOpen(false); setDockMenu(null); setContextMenu(null);
  };
  const handleDockContextMenu = (e, appId) => { e.preventDefault(); e.stopPropagation(); setDockMenu({ x: e.clientX, y: e.clientY, appId }); };
  const handleDesktopContextMenu = (e) => { e.preventDefault(); setContextMenu({ x: e.clientX, y: e.clientY }); };

  const activeAppName = activeWindowId ? (windows.find(w => w.id === activeWindowId)?.appId === 'about' ? 'System Information' : APPS.find(a => a.id === windows.find(w => w.id === activeWindowId)?.appId)?.name) : 'Finder';

  return (
    <div className={`w-full h-screen overflow-hidden relative select-none font-sans ${isDark ? 'text-white' : 'text-black'}`} onClick={handleBackgroundClick} onContextMenu={handleDesktopContextMenu}>
      <GlobalStyles />
      <div className="absolute inset-0 bg-cover bg-center transition-all duration-700" style={{ backgroundImage: `url(${wallpaper})` }} />
      {isLocked && <LockScreen wallpaper={wallpaper} onUnlock={() => setIsLocked(false)} isDark={isDark} />}
      <div className={`absolute top-0 left-0 right-0 h-8 px-4 flex items-center justify-between z-50 backdrop-blur-2xl text-sm shadow-sm border-b macos-transition ${isDark ? 'bg-black/40 border-white/5 text-white' : 'bg-white/40 border-white/20 text-black'}`}>
        <div className="flex items-center gap-4"><div className="relative group"><Apple size={16} className="mb-0.5 cursor-pointer hover:opacity-70" /><div className="absolute top-6 left-0 w-48 bg-white/90 dark:bg-gray-800/90 backdrop-blur-xl rounded-lg shadow-xl border border-black/5 dark:border-white/10 hidden group-hover:block py-1"><div className="px-4 py-1 hover:bg-blue-500 hover:text-white cursor-default" onClick={() => openApp('about')}>About This Mac</div><div className="h-px bg-gray-400/20 my-1 mx-2"></div><div className="px-4 py-1 hover:bg-blue-500 hover:text-white cursor-default" onClick={() => setIsLocked(true)}>Lock Screen</div></div></div><span className="font-bold">{activeAppName}</span>{['File', 'Edit', 'View', 'Go', 'Window', 'Help'].map(m => <span key={m} className="hidden sm:inline opacity-80 hover:opacity-100 cursor-default">{m}</span>)}</div>
        <div className="flex items-center gap-4">
           <div className="flex items-center gap-4 opacity-90">
             <DynamicBatteryIcon level={batteryLevel} isCharging={isCharging} isDark={isDark} />
             <Wifi size={16} />
             <Search size={16} className="cursor-pointer hover:scale-110 macos-transition" onClick={(e) => { e.stopPropagation(); setIsSpotlightOpen(!isSpotlightOpen); }} />
             <div className="cursor-pointer hover:scale-110 macos-transition" onClick={(e) => { e.stopPropagation(); setIsControlCenterOpen(!isControlCenterOpen); }}><LayoutGrid size={16} /></div>
           </div>
           <div className="text-xs font-medium leading-tight"><span>{currentTime.toLocaleDateString([], { weekday: 'short', month: 'short', day: 'numeric' })} {currentTime.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })}</span></div>
        </div>
      </div>

      <Spotlight isOpen={isSpotlightOpen} onClose={() => setIsSpotlightOpen(false)} onOpenApp={openApp} isDark={isDark} />
      <ControlCenter isDark={isDark} setIsDark={setIsDark} isOpen={isControlCenterOpen} />
      {dockMenu && <DockMenu {...dockMenu} onClose={() => setDockMenu(null)} onOpen={() => openApp(dockMenu.appId)} onQuit={() => quitApp(dockMenu.appId)} isDark={isDark} />}
      {contextMenu && (<div className={`absolute z-50 w-48 rounded-xl shadow-2xl backdrop-blur-xl border py-1 flex flex-col text-sm ${isDark ? 'bg-gray-800/90 border-gray-600' : 'bg-white/90 border-white/40'}`} style={{left: contextMenu.x, top: contextMenu.y}}><button className="text-left px-4 py-1.5 hover:bg-blue-500 hover:text-white" onClick={() => {openApp('settings'); setContextMenu(null)}}>Change Wallpaper...</button><button className="text-left px-4 py-1.5 hover:bg-blue-500 hover:text-white" onClick={() => setContextMenu(null)}>New Folder</button></div>)}
      <div className="absolute inset-0 pt-8 pb-24 z-0">{desktopItems.map(item => <DesktopIcon key={item.id} item={item} isSelected={selectedItemIds.includes(item.id)} onSelect={(id) => setSelectedItemIds([id])} onPositionChange={updateItemPos} />)}</div>
      {windows.map(w => <Window key={w.id} window={w} onClose={closeWindow} onMinimize={minimizeWindow} onMaximize={maximizeWindow} onFocus={focusWindow} updatePosition={updateWindowPos} isDark={isDark} setWallpaper={setWallpaper} setIsDark={setIsDark} wallpaper={wallpaper} notesContent={notesContent} setNotesContent={setNotesContent} />)}

      <div className="absolute bottom-4 left-0 right-0 flex justify-center z-50 pointer-events-none"><div className={`flex items-end gap-3 px-4 pb-3 pt-3 rounded-3xl backdrop-blur-2xl border shadow-2xl macos-transition pointer-events-auto ${isDark ? 'bg-gray-900/40 border-white/10' : 'bg-white/40 border-white/30'}`} onMouseLeave={() => setDockHoverIndex(null)}>{APPS.map((app, index) => { const scaleClass = dockHoverIndex === index ? "scale-125 -translate-y-4 mx-3" : (dockHoverIndex === index - 1 || dockHoverIndex === index + 1) ? "scale-110 -translate-y-1 mx-1" : ""; const isBouncing = bouncingAppId === app.id; return (<div key={app.id} className="relative flex flex-col items-center group">{dockHoverIndex === index && <div className="absolute -top-12 bg-gray-800/80 backdrop-blur text-white text-xs px-3 py-1.5 rounded-lg border border-white/10 shadow-xl mb-2 animate-in fade-in slide-in-from-bottom-2">{app.name}</div>}<button id={`dock-icon-${app.id}`} onClick={() => openApp(app.id)} onMouseEnter={() => setDockHoverIndex(index)} onContextMenu={(e) => handleDockContextMenu(e, app.id)} className={`w-12 h-12 rounded-2xl flex items-center justify-center shadow-lg dock-icon-transition origin-bottom ${scaleClass} ${isBouncing ? 'animate-bounce-icon' : ''} ${isDark ? 'bg-gray-800' : 'bg-white'} ring-1 ring-white/20 overflow-hidden`}>{app.isDynamic ? <CalendarIconDynamic /> : <app.icon className={`w-7 h-7 ${app.color}`} />}</button><div className={`w-1 h-1 rounded-full bg-white absolute -bottom-1.5 shadow-[0_0_5px_rgba(255,255,255,0.8)] macos-transition ${windows.some(w => w.appId === app.id) ? 'opacity-100' : 'opacity-0'}`} /></div>); })}</div></div>
      
      {isLaunchpadOpen && (<div className="absolute inset-0 z-50 bg-black/30 backdrop-blur-3xl flex flex-col items-center justify-center animate-in fade-in duration-500" onClick={(e) => {e.stopPropagation(); setIsLaunchpadOpen(false)}}><input type="text" placeholder="Search" className="w-64 bg-white/10 border border-white/20 text-white placeholder-white/60 rounded-xl px-4 py-2 mb-12 focus:outline-none focus:bg-white/20 backdrop-blur-md shadow-inner animate-in zoom-in-95 duration-500" onClick={e => e.stopPropagation()} /><div className="grid grid-cols-4 sm:grid-cols-6 gap-12">{APPS.map((app, i) => (<div key={app.id} className={`flex flex-col items-center gap-4 group cursor-pointer transition-transform hover:scale-105 animate-in zoom-in-50 fade-in duration-500 fill-mode-forwards`} style={{animationDelay: `${i * 30}ms`}} onClick={(e) => { e.stopPropagation(); openApp(app.id); }}><div className={`w-20 h-20 rounded-[22px] ${isDark ? 'bg-gray-800' : 'bg-white'} shadow-2xl flex items-center justify-center ring-1 ring-white/20`}><app.icon size={44} className={app.color} /></div><span className="text-white text-sm font-medium drop-shadow-md">{app.name}</span></div>))}</div></div>)}
    </div>
  );
}
