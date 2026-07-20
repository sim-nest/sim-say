# SIM

In one line: an expandable Rust runtime whose pieces talk through shared values.

SIM keeps a small, steady center and lets useful behavior arrive as libraries.
A codec, view, stream, number kind, model, or device joins the system without
becoming a special case. This brochure is the plain-language tour of what each
piece gives you.

## The constellation by what it does for you

### agents

- **sim-lib-agent** -- The part of SIM that lets an assistant use tools, remember things, and pick which model answers.
- **sim-lib-agent-runner-core** -- The shared rulebook that lets any model, from any provider, plug into SIM the same way.
- **sim-lib-agent-runner-http** -- The connector that lets SIM reach hosted and local models through provider-shaped HTTP profiles.
- **sim-lib-agent-runner-local** -- The piece that lets SIM run a model right on your own machine, in the same process.
- **sim-lib-agent-runner-process** -- The connector that lets SIM use a model or tool that runs as a separate program on your computer.
- **sim-lib-bridge** -- It keeps model-facing BRIDGE packets from leaving or entering SIM unless their local checks agree.
- **sim-lib-cookbook** -- A built-in collection of worked recipes you can browse, search, and actually run inside SIM.
- **sim-lib-forge** -- It compiles a plain-English task into a reusable, checked model program you can trust and cache instead of re-prompting.
- **sim-lib-mcp** -- The piece that turns SIM's own tools and skills into safe listings other assistants can discover.
- **sim-lib-openai-server** -- A gateway that lets OpenAI-shaped clients reach SIM's model and agent surface.
- **sim-lib-server** -- The part of SIM that serves evaluation and agents to callers and streams the replies back.
- **sim-lib-skill** -- The system that describes each thing an agent can do and lets it call that ability like any other command.
- **sim-lib-stream-fabric** -- The layer that lets SIM place work on other machines and share streaming results without minding where they run.
- **sim-mcp-server** -- A ready-to-run program that lets other assistants reach SIM through the common Model Context Protocol.
- **sim-table-remote** -- The piece that makes a table living on another machine look and act like a local table in SIM.

### audio

- **sim-lib-audio-dsp** -- A kit of ready-made sound-shaping blocks -- gain, filters, delay, and dynamics -- that you drop into a signal path.
- **sim-lib-audio-graph-core** -- The patch bay that connects your sound-shaping blocks into one signal flow and renders it start to finish.
- **sim-lib-audio-graph-live** -- The engine that runs your effect chain in real time, feeding a sound card without stutters or dropouts.
- **sim-lib-plugin-clap** -- A way to shape a SIM effect so it looks and behaves like a CLAP plugin, and to run CLAP-shaped effects inside SIM.
- **sim-lib-plugin-core** -- The shared language for describing an audio plugin -- its name, its knobs, and the settings you save and recall.
- **sim-lib-plugin-lv2** -- A way to shape a SIM effect so it looks and behaves like an LV2 plugin, and to run LV2-shaped effects inside SIM.
- **sim-lib-plugin-vst3** -- A way to describe a SIM effect in the shape of a VST3 plugin, worked out entirely in Rust with no native binary.
- **sim-lib-plugin-wasm** -- A way to load audio plugins packaged as WebAssembly and run them as ordinary SIM effects.
- **sim-lib-stream-alsa** -- A stand-in for the low-level Linux ALSA sound system that lets SIM audio run and be tested without real hardware.
- **sim-lib-stream-asio** -- A stand-in for the Windows ASIO low-latency sound system that lets SIM audio run and be tested without real drivers.
- **sim-lib-stream-coreaudio** -- A stand-in for Apple's CoreAudio sound system that lets SIM audio run and be tested without a Mac or its frameworks.
- **sim-lib-stream-cpal** -- A cross-platform sound-card connection for SIM, with a hardware-free default lane and an optional path to real devices.
- **sim-lib-stream-jack** -- A stand-in for the JACK audio routing system that lets SIM connect and be tested without a running JACK server.
- **sim-lib-stream-jack-provider** -- A registrable JACK sound provider for SIM, modeled by default and hardware-gated when real JACK is available.
- **sim-lib-stream-pipewire** -- A stand-in for PipeWire, the modern Linux sound server, that lets SIM connect and be tested without a running daemon.
- **sim-lib-stream-portaudio** -- A stand-in for PortAudio, the portable sound layer, that lets SIM play and be tested without a PortAudio install.
- **sim-lib-daw-session** -- A recording-studio session you can build, arrange, and bounce to audio without opening any studio software.
- **sim-lib-midi-ble** -- A way to find and talk to wireless Bluetooth MIDI controllers, or to rehearse that link from saved fixtures when no adapter is around.
- **sim-lib-midi-core** -- The shared vocabulary of MIDI -- notes, timing, and control messages -- that every other music tool in SIM speaks.
- **sim-lib-midi-live** -- Fast in-and-out buffers that let live MIDI flow through your setup without stalling when things get busy.
- **sim-lib-midi-rtmidi** -- A bridge to the MIDI ports on your computer, with a stand-in mode for testing when no gear is plugged in.
- **sim-lib-midi-shapes** -- A tidy text form for MIDI so events, tracks, and whole files can be written down, read back, and handled as first-class objects.
- **sim-lib-midi-smf** -- Reads and writes ordinary .mid files, the standard way music moves between programs.
- **sim-lib-midi-sysex** -- Makes sense of the maker-specific MIDI messages that carry synth patches and tuning tables, turning raw bytes into readable settings.
- **sim-lib-midi-wasm-frame** -- Compact, frame-safe descriptions of MIDI data ready to hand across to a browser or plugin boundary.
- **sim-lib-music-analysis** -- Looks at a piece of music and reveals its structure -- what chords are sounding and how the notes move moment to moment.
- **sim-lib-music-combinators** -- A shelf of generative players -- arpeggiators, basslines, drum patterns, step sequencers -- that turn simple inputs into steady streams of notes.
- **sim-lib-music-core** -- The heart of the music world in SIM: notes, chords, melodies, and scores, plus the timeline they live on.
- **sim-lib-music-lift** -- Raises a plain MIDI file into something richer -- a readable piano roll, a chord progression, or separated voices.
- **sim-lib-music-lower** -- Takes a structured piece of music and renders it back down into a playable MIDI file.
- **sim-lib-music-notation** -- Turns a score into readable notation text and reads it back, using a familiar LilyPond-style form.
- **sim-lib-music-shapes** -- Gives every music object a readable text form and makes it a first-class object the SIM runtime can hold and match.
- **sim-lib-music-synth** -- A kit of software synthesizers -- from a DX7-style FM engine to modular System 55 and 700 rigs -- that you can play entirely in code.
- **sim-lib-music-transform** -- Reworks musical material with the classic moves -- transpose, invert, reverse, stretch, and compress.
- **sim-lib-music-wasm-frame** -- Frame-safe descriptions of music objects, ready to carry across to a browser or plugin without dragging the whole engine along.
- **sim-lib-pitch-chord** -- Builds chords from notes, scale degrees, or jazz symbols, voices them, and can harmonize a melody for you.
- **sim-lib-pitch-core** -- The basic alphabet of pitch -- notes, note names, octaves, and the distances between them -- that the rest of the theory tools share.
- **sim-lib-pitch-dissonance** -- Scores how tense or restful a group of notes sounds, from several theoretical points of view at once.
- **sim-lib-pitch-namer** -- Names a group of notes in every musical language at once -- and translates a name from one school to another.
- **sim-lib-pitch-namer-forte** -- Gives any group of notes its Forte set-class name, the standard label set theory uses.
- **sim-lib-pitch-namer-jazz** -- Reads and recognises jazz chord symbols, turning names like Cmaj7 or Am7/G into chords and back.
- **sim-lib-pitch-namer-riemann** -- Labels a triad by its function -- major or minor tonic -- in the neo-Riemannian style.
- **sim-lib-pitch-namer-roman** -- Reads a chord in the context of a key and names its scale degree -- I, V7, and so on -- the way theory class does.
- **sim-lib-pitch-scale** -- Defines scales and modes and can snap incoming notes onto the scale you choose.
- **sim-lib-pitch-set** -- Packs a group of pitches into a compact bit pattern and runs the set-theory operations on it fast.
- **sim-lib-pitch-shapes** -- Gives pitches, scales, chords, and keys a readable text form and makes them objects the SIM runtime can hold.
- **sim-lib-pitch-wasm-frame** -- Frame-safe descriptions of pitch data, ready to carry across to a browser or plugin boundary.
- **sim-lib-sound-audio-lift** -- Listens to raw audio and works out the notes hiding inside it.
- **sim-lib-sound-bridge** -- Connects MIDI notes to actual sound, deciding which instrument, tuning, and voice each note plays through.
- **sim-lib-sound-core** -- The basic building blocks of sound -- frequency, loudness, and the ingredients of a tone.
- **sim-lib-sound-dissonance** -- Estimates how rough or smooth two or more sounds are together, using established psychoacoustic models.
- **sim-lib-sound-gm** -- The standard General MIDI instrument and drum set, so program numbers map to the sounds everyone expects.
- **sim-lib-sound-render** -- Turns synthesized tones into real audio samples and writes them out as a WAV file.
- **sim-lib-sound-shapes** -- Gives every sound ingredient -- tones, spectra, timbres, tunings -- a readable text form and makes it a runtime object.
- **sim-lib-sound-spectrum** -- Breaks a sound into its frequencies and measures its character -- brightness, peaks, and how it changes.
- **sim-lib-sound-timbre** -- A library of instrument voices and the filters that colour them, from pure sines to plucked strings and bells.
- **sim-lib-sound-tuning** -- A collection of tuning systems, from modern equal temperament to historical temperaments, that decide the exact pitch of every note.
- **sim-lib-sound-wasm-frame** -- Frame-safe descriptions of sound data, ready to carry across to a browser or plugin boundary.
- **sim-lib-stream-bridge** -- Converts flowing streams between MIDI and audio so one kind of stream can feed the other.
- **sim-lib-stream-file** -- Reads and writes streams to and from files on disk, with each access recorded and permission-checked.
- **sim-lib-stream-midi** -- Wraps live MIDI sources and sinks so they plug into the SIM streaming pipeline as ordinary packets.

### auto

- **sim-codec-uds** -- a safe diagnostic byte-frame reader for automotive UDS and OBD-II data.
- **sim-lib-auto-core** -- the automotive vocabulary SIM uses to name vehicles, shop lanes, effects, and access rules.
- **sim-lib-auto-diag** -- a safe diagnostic fabric that lets SIM read modeled vehicle data and replay it exactly.
- **sim-lib-auto-vehicle** -- a vehicle identity lookup layer that keeps workshop data sources behind explicit network contracts.
- **sim-lib-auto-vendor** -- a manifest-driven vendor engine that keeps vehicle-side actions behind explicit proof gates.

### codecs

- **sim-codec** -- It is the shared workshop that lets every SIM format read text or bytes in and write them back out.
- **sim-codec-algol** -- It lets you read and write values in familiar infix notation, the ordinary style where symbols sit between their operands.
- **sim-codec-binary** -- It packs any value into a small, tagged stream of bytes and reads it straight back.
- **sim-codec-binary-base64** -- It carries the compact binary form as plain text, so it can travel anywhere only text is allowed.
- **sim-codec-bitwise** -- It writes any value in the smallest, most predictable string of bits, the same value always giving the same result.
- **sim-codec-bitwise-base64** -- It carries the canonical minimal bit-packed form as plain text, so it can travel anywhere only text is allowed.
- **sim-codec-bridge** -- It gives SIM, people, and model seats one checked packet format for requests, replies, reviews, and receipts.
- **sim-codec-chat** -- It reads and writes model conversations -- prompts, replies, and events -- in one neutral, provider-independent form.
- **sim-codec-compare** -- the honest scoreboard that tells you when the bit-packed wire format actually beats the plain one, and when it just wastes your time.
- **sim-codec-config** -- It turns small SIM configuration files into ordinary runtime maps and writes those maps back as clean text.
- **sim-codec-doc** -- It reads and writes Markdown, Typst, AsciiDoc, and LaTeX as one structured document value.
- **sim-codec-json** -- It reads and writes any value as JSON, so SIM data flows through the world's most common interchange format.
- **sim-codec-lisp** -- It reads and writes values in parenthesized s-expression text, the plain nested form where structure is spelled out with brackets.
- **sim-codec-lua** -- It gives SIM a bounded Lua chunk reader and writer that keeps source tied to the shared expression graph.
- **sim-codec-mcp** -- It reads and writes the message envelopes of the Model Context Protocol, checking each one is well formed.
- **sim-codec-pratt** -- It gives SIM codecs a shared way to group infix tokens into expression trees.
- **sim-test-support** -- It is the shared set of helpers the SIM formats use to test that they read and write values correctly.
- **sim-wasm-abi** -- It is the shared handshake that lets SIM pass values to and from sandboxed WebAssembly modules.

### core

- **sim-kernel** -- the small, steady center that lets every SIM piece connect.
- **sim-citizen** -- The layer that lets a domain's own data types show up as first-class, well-behaved values inside SIM.
- **sim-citizen-derive** -- A one-line marker that writes all the wiring needed to make your data type a full SIM value for you.
- **sim-config** -- layered SIM settings stay inspectable because every source becomes the same table-shaped data before it is merged.
- **sim-cookbook** -- The engine behind SIM's built-in lessons that teach each library from the inside.
- **sim-lib-net-core** -- The quiet reading room that turns raw web traffic into clean, understandable pieces.
- **sim-lib-surface-card** -- The shared name-translator that presents SIM's tools cleanly to outside systems and people.
- **sim-macros** -- A set of labels that let an author declare SIM building blocks in plain Rust and have the wiring written for them.
- **sim-table-core** -- The shared rulebook for naming and requesting table data across SIM.
- **sim-value** -- A friendly toolkit for building and reading the small data shapes that flow through SIM.
- **sim-shape** -- it is the single component that decides whether a piece of data fits a described pattern, and tells you exactly what it found inside.

### math

- **sim-lib-numbers-ad** -- It works out how fast a calculation changes without you ever doing calculus by hand.
- **sim-lib-numbers-arith** -- It lets you add, subtract, multiply, and divide numbers of different kinds together and always get the right answer.
- **sim-lib-numbers-bigint** -- It handles whole numbers of any size, far beyond what an ordinary calculator can hold.
- **sim-lib-numbers-bool** -- It gives you plain true-and-false values that slot neatly into the rest of the math.
- **sim-lib-numbers-cas** -- It lets you work with math as symbols and formulas, not just crunched-down numbers.
- **sim-lib-numbers-cas-diff** -- It does calculus on your formulas, finding derivatives and integrals as tidy new expressions.
- **sim-lib-numbers-cas-eval** -- It takes a symbolic formula and works out its value once you supply what the unknowns stand for.
- **sim-lib-numbers-codec** -- It is how a new kind of number announces itself so the system knows how to read and write it.
- **sim-lib-numbers-complex** -- It gives you complex numbers, the two-part numbers that engineering and physics rely on.
- **sim-lib-numbers-core** -- It is the shared groundwork that lets every kind of number in the system behave consistently.
- **sim-lib-numbers-exotic** -- It represents numbers to unlimited precision by unfolding them only as far as you actually need.
- **sim-lib-numbers-f64** -- It gives you everyday decimal numbers, the fast, general-purpose values most calculations use.
- **sim-lib-numbers-fixed** -- It offers whole numbers in specific sizes, so you can match the exact range and storage a task needs.
- **sim-lib-numbers-float** -- It provides compact decimal numbers that trade a little accuracy for smaller size and speed.
- **sim-lib-numbers-func** -- It turns a function itself into a value you can name, pass around, and call whenever you like.
- **sim-lib-numbers-i64** -- It provides the standard whole numbers, positive and negative, that most counting and indexing use.
- **sim-lib-numbers-numeric** -- It solves the hard calculus problems by careful number-crunching when a neat formula is out of reach.
- **sim-lib-numbers-prelude** -- It switches on the whole math toolkit in a single step, so everything is ready at once.
- **sim-lib-numbers-quad** -- It measures the area under a curve and estimates slopes by clever, careful sampling.
- **sim-lib-numbers-rational** -- It keeps fractions exact, so one-third really stays one-third instead of a rounded decimal.
- **sim-lib-numbers-rk** -- It follows how a changing system moves over time, step by careful step.
- **sim-lib-numbers-stats** -- It summarizes your data with averages, spreads, probabilities, and fairness checks.
- **sim-lib-numbers-tensor** -- It gives you grids of numbers, from simple lists to multi-dimensional blocks, as one kind of value.
- **sim-lib-numbers-tensor-bcast** -- It lets you combine grids of different shapes sensibly, stretching the smaller to match the larger.
- **sim-lib-numbers-tensor-bit** -- It stores big grids of yes-or-no values tightly packed and combines them with logical operations.
- **sim-lib-numbers-tensor-cmplxf** -- It holds grids of complex numbers efficiently, for signal and wave work done in bulk.
- **sim-lib-numbers-tensor-f64** -- It gives you fast grids of ordinary decimal numbers, the common case for number-heavy work.
- **sim-lib-numbers-tensor-i64** -- It gives you fast grids of whole numbers that never overflow into wrong answers.
- **sim-lib-numbers-tensor-linalg** -- It does the matrix and vector math behind graphics, data science, and engineering.
- **sim-lib-numbers-tensor-rat64** -- It gives you grids of exact fractions, so array math avoids rounding entirely.
- **sim-lib-discrete** -- one front door to the whole discrete-math family, where you switch on only the parts you need.
- **sim-lib-discrete-algebra** -- one calculation core that answers many discrete-math questions by changing what "add" and "multiply" mean.
- **sim-lib-discrete-comb** -- count and list every way to arrange or choose things, and give each arrangement its own exact number.
- **sim-lib-discrete-graph** -- model anything as a network of connections and find out how the pieces link, reach, and cost.
- **sim-lib-discrete-rank** -- turn a discrete object into a position and a grade so you can place it, score it, and compare it.
- **sim-lib-discrete-spectral** -- break a pattern over on-or-off choices into its building blocks and read how it is really shaped.
- **sim-lib-femm-assembly** -- It gathers every small piece of your model into one big system the computer can actually solve.
- **sim-lib-femm-codec** -- It writes your model and its results out as readable text and reads them back without losing anything.
- **sim-lib-femm-core** -- It is the shared vocabulary and foundation every other finite-element piece builds on.
- **sim-lib-femm-field** -- It reads a solved model and tells you the field values anywhere you point.
- **sim-lib-femm-fixtures** -- It is a set of ready-made test problems whose right answers are already known.
- **sim-lib-femm-flow** -- It patiently drives a stubborn, nonlinear model to a settled answer and tells you how it went.
- **sim-lib-femm-function** -- It turns a whole model into a simple knob-in, answer-out function you can call.
- **sim-lib-femm-geometry** -- It is where you draw the two-dimensional shape you want to study.
- **sim-lib-femm-material** -- It is where you say what each part is made of and what is pushing on it.
- **sim-lib-femm-mesh** -- It divides your shape into a fine web of triangles and checks the model makes sense first.
- **sim-lib-femm-ode** -- It follows your model through time as the world around it keeps changing.
- **sim-lib-femm-physics** -- It holds the actual laws of nature the simulation obeys, one set per kind of problem.
- **sim-lib-femm-post** -- It turns a finished solve into the real-world numbers you actually wanted to know.
- **sim-lib-femm-prelude** -- It switches on the whole finite-element toolkit in a single step.
- **sim-lib-femm-query** -- It keeps every FEMM answer path speaking the same model-query language.
- **sim-lib-femm-sensitiv** -- It tells you how much your result would shift if you nudged each design setting.
- **sim-lib-femm-solve** -- It takes a described model all the way to a solved answer and hands you proof it was done right.
- **sim-lib-femm-space** -- It works out the fine geometric details inside each triangle so the solver knows how values vary across it.
- **sim-lib-femm-tape** -- It remembers work already done so repeated solves do not start from scratch every time.

### runtime

- **sim-lib-binding** -- It keeps track of what every name in a program stands for, and exactly where that meaning holds.
- **sim-lib-control** -- It manages how a running program moves -- pausing, resuming, retrying, and recovering when something goes wrong.
- **sim-lib-core** -- It is the shared plumbing every SIM library uses to announce what it offers and get it installed once, cleanly.
- **sim-lib-dispatch** -- It picks the right version of an operation based on the kinds of things you hand it.
- **sim-lib-exec** -- It lets a trusted host run a specific outside process with clear permission and tight limits.
- **sim-lib-lang-cl** -- It lets you write for SIM in familiar Common Lisp style, with the parentheses and forms Lisp people expect.
- **sim-lib-lang-clojure** -- It lets you write for SIM in Clojure style, using EDN data notation and an immutable, functional feel.
- **sim-lib-lang-genconf** -- It generates a steady, repeatable set of test inputs for confirming that language surfaces behave correctly.
- **sim-lib-lang-islisp** -- It lets you write for SIM in ISLISP, the small standardized Lisp with a deliberately compact core.
- **sim-lib-lang-julia** -- It lets you write for SIM in Julia style, the notation favored for technical and numerical work.
- **sim-lib-lang-lua** -- It lets you write for SIM in Lua style, the small, approachable scripting notation many people already know.
- **sim-lib-lang-matrix** -- It gathers every language surface and checks them all against one shared standard so they agree.
- **sim-lib-lang-prolog** -- It lets you write for SIM in Prolog style, stating facts and rules and letting the system find the answers.
- **sim-lib-lang-ruby** -- It lets you write for SIM in an expressive Ruby style, with the readable, block-friendly flavor Ruby is known for.
- **sim-lib-lang-scheme** -- It lets you write for SIM in Scheme, the small, clean Lisp dialect of the R7RS-small standard.
- **sim-lib-lang-typed-lazy** -- It lets you write for SIM in a typed, lazy style where values are checked ahead and computed only when needed.
- **sim-lib-logic** -- It lets you state facts and rules, then ask questions and get every answer that fits.
- **sim-lib-mutation** -- It lets programs change data in place while keeping every change tracked and permitted.
- **sim-lib-namespace** -- It organizes names into separate modules so large programs do not trip over each other.
- **sim-lib-pattern** -- It takes data apart by its shape and handles each case, warning you when a case is missed.
- **sim-lib-sequence** -- It works with collections of items -- even endless ones -- without copying them over and over.
- **sim-lib-standard-core** -- It is the batteries-included default bundle that makes SIM useful the moment it starts.
- **sim-list-cell** -- A classic linked-list store that holds items in order so a program can keep and change sequences.
- **sim-list-lazy** -- A list that figures out its contents only when you ask, so huge or endless sequences cost little until read.
- **sim-table-db** -- A file-cabinet style store that keeps named values in a tree of folders you reach by path.
- **sim-table-fs** -- Turns a folder on disk into a lookup table where each entry is a file and each subfolder is a nested table.
- **sim-table-hash** -- A quick name-to-value lookup store that finds any entry by its key almost instantly.
- **sim-table-http** -- It lets a trusted host treat direct HTTP resources as table entries under explicit network permission.
- **sim-table-lazy** -- A lookup table whose values are worked out the first time you ask and then remembered.
- **sim-table-override** -- A stack of lookup tables where the top layers can cover entries in the ones beneath.
- **sim-ledger** -- clear yearly books with exact money values and balance checks at the center.
- **sim-ledger-cli** -- a direct terminal path from exported books to checked yearly reports.
- **sim-ledger-odb** -- bring LibreOffice Base bookkeeping exports into the ledger model without changing the books by hand.
- **sim-lib-ledger-books** -- a review desk for bookkeeping drafts before they enter the books.
- **sim-lib-ledger-close** -- exact year-end statements from local ledger files.

### stream

- **sim-lib-rank** -- A way to give every item in a well-defined space an exact number, so collections can be ordered and searched.
- **sim-lib-stream-audio** -- The part that turns raw sound samples into observable streams and back again.
- **sim-lib-stream-clock** -- The part that lines up a stream of data with real time or musical beats.
- **sim-lib-stream-combinators** -- The building blocks for reshaping and combining streams of data as they flow.
- **sim-lib-stream-core** -- The shared shape for a run of changing data, so anything that moves can be watched packet by packet.
- **sim-lib-stream-device** -- A hardware-free device sample lane, so sensors can be modeled and tested before any real device is attached.
- **sim-lib-stream-prelude** -- The ready-made bundle that makes SIM's whole streaming toolkit available in one install.
- **sim-lib-topology** -- The part that turns a described network of connected steps into a checked, ready-to-run plan.
- **sim-lib-stream-host** -- It plugs SIM's live streams into the real audio and MIDI gear on your machine and across your network.

### surface

- **sim-lib-repl** -- The interactive prompt where you type a line and SIM answers back.
- **sim-run** -- The `sim` program you launch from a terminal to start a SIM session.
- **sim-run-core** -- The part that reads your command line and sets up the SIM session.
- **sim-run-loaders** -- The pieces that let SIM pull in source files, packs, and outside plug-ins.
- **sim-view-tty** -- The library that draws SIM in your terminal and reads your keystrokes.
- **sim-conformance** -- the runnable checklist that proves SIM actually behaves the way its architecture promises.
- **sim-nest** -- the single starting point a developer adds to reach every part of the SIM runtime.
- **sim-codec-mspdi** -- project schedules can cross the Microsoft Project XML boundary with clear loss reporting.
- **sim-codec-odf** -- LibreOffice files can carry local office documents without hiding what falls outside the portable model.
- **sim-codec-ooxml** -- Office file packages can move through SIM without hiding what the portable model cannot keep.
- **sim-lib-deck** -- presentation content stays portable before it enters a slide file or hosted editor.
- **sim-lib-doc-core** -- the small document spine that office codecs, stores, views, and sites share.
- **sim-lib-doc-ledger** -- a careful handoff from office evidence to accounting reviews.
- **sim-lib-doc-markup** -- article files enter the office document flow through the same markup body.
- **sim-lib-doc-site** -- the office bridge that makes external document places loadable without making them the frontend.
- **sim-lib-doc-store** -- a local office document cache that keeps edits tied to the ledger that produced them.
- **sim-lib-doc-surface** -- a suite-facing document surface that turns office records into renderable panes and checked edits.
- **sim-lib-gantt** -- local project schedules that can be checked and reopened without a vendor system.
- **sim-lib-mail** -- mail and calendar records stay useful without carrying private bodies around.
- **sim-lib-office-pack** -- It packages a closed ledger year into review-ready office exports without sending anything live.
- **sim-lib-sheet** -- spreadsheets keep exact local values before any vendor file format enters.
- **sim-site-dalux** -- Dalux project items become local SIM office records behind API identity gates.
- **sim-site-libreoffice** -- LibreOffice automation stays optional, permissioned, and outside the runtime process.
- **sim-site-msgraph** -- Microsoft Graph documents can enter SIM through a modeled-first office site.
- **sim-site-powerproject** -- Powerproject and Project for the web become permissioned places for SIM Gantt plans.
- **sim-site-sharepoint** -- SharePoint lists and drive folders become reviewable SIM office records.

### web

- **sim-lib-intent** -- it turns a click, drag, or typed edit into a clear request the system can check before anything changes.
- **sim-lib-scene** -- it is the portable picture of what should appear on screen, saved as plain data you can inspect and share.
- **sim-lib-view** -- it decides how any value should be shown and edited, and always has a sensible default ready.
- **sim-lib-view-agent** -- it lets you wire up and watch a network of agents on a canvas, live, alongside the agents themselves.
- **sim-lib-view-bridge** -- it lets people review and change BRIDGE packets in the same form agents use.
- **sim-lib-view-codec** -- it shows one value written several ways at once and lets you inspect how it matches a shape.
- **sim-lib-view-daw** -- it brings a full music studio -- timeline, mixer, effects, and synths -- into the browser workspace.
- **sim-lib-view-device** -- it turns open surface claims into a clear device envelope, so small screens and wearable edges degrade honestly.
- **sim-lib-view-doc** -- it is a writing surface where article structure, equations, figures, source text, and live results stay together.
- **sim-lib-view-math** -- it turns numbers, matrices, and formulas into plots and grids you can see and adjust.
- **sim-lib-view-wasm-frame** -- it is the local helper that renders a value to a screen picture, folds your gestures into edits, and commits them in place.
- **sim-lib-web-bridge** -- it is the pipe that carries your edits out and the fresh pictures back, no matter where the runtime actually runs.
- **sim-lib-web-layout** -- it holds the whole arrangement of your workspace -- panes, tabs, and docks -- as data you can save and restore.
- **sim-web-shell** -- it is the program you run to open the SIM workspace in a browser.

## Every crate at a glance

### sim-agent-net

#### sim-lib-agent

The part of SIM that lets an assistant use tools, remember things, and pick which model answers.

This is the home base for agents inside SIM. It brings together the pieces an assistant needs to do real work: the tools it can call, the memory it keeps between turns, the patterns that shape its behavior, and the fixtures for trying things out safely. It also decides where a model request actually runs, choosing from a catalog of placements you have set up, whether that is a model on your own machine or one reached across a network. When a request has been answered once, it can keep that reply and hand back the same result for the same question, so you are not paying to ask twice. Everything stays fair and orderly when many requests arrive at once.

#### sim-lib-agent-runner-core

The shared rulebook that lets any model, from any provider, plug into SIM the same way.

This crate sets the common ground that every model connection in SIM agrees on. It describes what a request to a model looks like, what a finished reply looks like, and how progress can arrive piece by piece while an answer is still being written. It also describes how a model announces what it can do and how the system picks one model over another when several could answer. None of this is tied to a particular company or service. Because the shape is fixed and neutral, one place can swap a local model for a hosted one, or route between several, without any of the surrounding code needing to learn a new set of terms.

#### sim-lib-agent-runner-http

The connector that lets SIM reach hosted and local models through provider-shaped HTTP profiles.

This crate lets SIM talk to a model that lives behind a web address. You point it at a service, and it handles the back-and-forth: sending your request, reading the reply, and passing along partial text as it streams in so you do not wait for the whole answer. It understands hosted OpenAI and Anthropic services, local Ollama, LM Studio, and Lemonade servers, and other OpenAI-compatible endpoints. It also takes care to keep sensitive parts of a request, such as keys and private content, from leaking into logs and traces. From SIM's point of view, each provider becomes just another runner it can call.

#### sim-lib-agent-runner-local

The piece that lets SIM run a model right on your own machine, in the same process.

This crate installs a model runner that lives inside SIM itself, registered under a local placement so agents can send work to it. Out of the box it needs no model files and makes no outside contact, which makes it a safe, predictable default for trying things and for tests where you want the same answer every time. When you do want real on-device inference, an optional build brings in native model support, kept fenced off in one clearly marked spot. Another optional build can host a model packaged as a sandboxed guest, loaded only after capability checks pass. The runner announces what it offers, including whether it can stream and whether replies can be reused.

#### sim-lib-agent-runner-process

The connector that lets SIM use a model or tool that runs as a separate program on your computer.

This crate lets SIM drive a model by launching a local program and talking to it through its input and output. SIM sends the request in, the program does its work, and SIM reads the result back. It supports both a plain text conversation and a structured exchange where the request and reply are passed as JSON, and it can read the program's output line by line so streamed answers arrive as they are produced. This is the natural way to wire in a command-line model tool, a script, or any local helper that reads a request and prints a reply, without that tool needing to know anything about SIM.

#### sim-lib-bridge

It keeps model-facing BRIDGE packets from leaving or entering SIM unless their local checks agree.

This crate is the runtime guard around BRIDGE packets. On send, it stamps a stable identity, proves the line form can be read back, checks that every byte belongs to the packet, and runs the same receive checks the other side will use. When an answer comes back, it reads the final model content as another BRIDGE packet and checks the move, parts, capabilities, and declared return contract before accepting it.

#### sim-lib-cookbook

A built-in collection of worked recipes you can browse, search, and actually run inside SIM.

This crate turns SIM's recipe collection into live commands you can use while the system is running. You can list the books and chapters, look up a specific recipe, search across them, and step to the next one in a sequence. Recipes are more than reading material: a recipe can be run, and when it runs SIM reads its setup, carries it out, and checks that the results match what the recipe promised. That makes each recipe a small, self-checking example rather than a snippet you copy by hand and hope works. The same shared collection feeds the command line, the web view, and the help and browse surfaces, so everyone sees one consistent set of examples.

#### sim-lib-forge

It compiles a plain-English task into a reusable, checked model program you can trust and cache instead of re-prompting.

FORGE turns prose into a named, verified artifact. You hand it a task in ordinary language; it lifts that prose into a BRIDGE packet, confirms the packet is well-formed and types its own output, then checks the answer contract with real verifiers before the result is trusted. A task that passes becomes a golden artifact with a stable identity, so the next caller fetches the compiled program instead of asking a model to interpret the same words again. It also routes work to a cheap model first and only escalates when a check fails, and it can measure whether compiling actually helped.

#### sim-lib-mcp

The piece that turns SIM's own tools and skills into safe listings other assistants can discover.

The Model Context Protocol is a common way for assistants to find out what tools and resources are available to them. This crate takes SIM's internal catalog, its browse cards and its skill descriptions, and presents each one as a tidy, protocol-shaped listing. As it does so it strips out details that should not be shared, so what goes out is a redacted, presentable summary rather than raw internals. The result is a clean inventory of what SIM can offer to an outside assistant, described in terms that assistant already understands, without exposing the machinery behind each entry.

#### sim-lib-openai-server

A gateway that lets OpenAI-shaped clients reach SIM's model and agent surface.

Many programs already know the request and response shapes used by OpenAI-style model services. This crate gives SIM a gateway in that shape for chat, response, embedding, model listing, streaming, replay, and inspection flows. It also includes SIM fixture and subset routes for file records, audio transcription and speech, image references, and text-vector search, so tests and demos can exercise those object families without pretending to be a full media or multipart provider. Stored responses can be fetched again by id, replayed, or branched for inspection. The model listing reports the models SIM actually has available, so local, fixture, and remote model entries appear together when they are installed.

#### sim-lib-server

The part of SIM that serves evaluation and agents to callers and streams the replies back.

This crate lets SIM act as a service. A caller can ask it to evaluate work, receive replies as a stream, and run agent loops, all across the runtime. It provides the places where work can run, whether locally, as a coroutine, through a pipeline, in a loop, or spread across a fabric, along with the routing, connections, and conversational drivers that carry requests in and answers out. By default it stays entirely in-process and opens no network at all, which keeps a plain setup simple and closed. When you actually want to accept requests over the network, an HTTP transport is available as an explicit opt-in, and inbound triggers are added the same deliberate way.

#### sim-lib-skill

The system that describes each thing an agent can do and lets it call that ability like any other command.

A skill is any capability an agent can reach for: a tool, a model, a stored memory, a retriever, a judge that scores answers, a router that picks a path, and more. This crate gives every skill a clear description that pairs a stable name with the shape of what it takes in and gives back, along with rules about caching, recording, and privacy, and the backend that actually runs it. Skills are gathered into a registry and then behave like ordinary callable objects, so an agent invokes an ability the same simple way whether it lives in a fixture, a web service, a local program, or another assistant. Optional pieces select which backends and integrations you want.

#### sim-lib-stream-fabric

The layer that lets SIM place work on other machines and share streaming results without minding where they run.

This crate lets SIM spread evaluation across a group of machines while the code asking for that work stays unaware of where it happens. It carries streams between peers, packing them into bounded messages for the trip and unpacking them on arrival, with control signals to open, advance, pause, cancel, and report on each stream. Its central idea is simple: a finished reply is saved by the exact question that produced it, so any machine that already holds that answer can serve it, and asking becomes a matter of finding who holds a given result rather than tracking a routing map. Because a saved answer never changes, the record of who holds what needs no central agreement and heals itself by replaying its log. Sensitive inputs are hidden before work is placed elsewhere.

#### sim-mcp-server

A ready-to-run program that lets other assistants reach SIM through the common Model Context Protocol.

This crate is a standalone program that puts SIM on the other end of the Model Context Protocol, the shared way assistants discover and call tools. You start it, it reads its options, and it builds a running SIM with the protocol's codec and library already in place, then serves that protocol over a standard input and output channel. The result is a single command that exposes SIM's tools and skills to any assistant able to speak this protocol, with no extra assembly on your part. It is the packaged, launch-and-go form of SIM's protocol support, meant to be pointed at and used rather than built up from parts.

#### sim-table-remote

The piece that makes a table living on another machine look and act like a local table in SIM.

This crate lets SIM treat a table that actually lives somewhere else as if it were right at hand. It presents a remote table as an ordinary table object, so the code that reads and works with it does not need to know the data sits on another machine. Alongside the table it provides a small record that describes what the remote table is, and the adapter that connects the local view to the remote source behind it. The effect is that distance disappears from the caller's point of view: you work with the table through the same everyday moves you would use for one held locally, and the crossing of the gap is handled underneath.

### sim-audio-daw

#### sim-lib-audio-dsp

A kit of ready-made sound-shaping blocks -- gain, filters, delay, and dynamics -- that you drop into a signal path.

This is a stocked shelf of the tone-shaping tools an audio project reaches for again and again. You get level and pan controls, gentle smoothing so knob moves never click, one-pole and biquad and state-variable filters for carving tone, a delay line with comb and all-pass building blocks, and modulation colours like chorus, flanger, and vibrato. On the dynamics side there is a compressor, gate, limiter, soft clipper, and waveshaper. Every block is plain math with no hardware attached, so it sounds the same whether you preview it or run it live.

#### sim-lib-audio-graph-core

The patch bay that connects your sound-shaping blocks into one signal flow and renders it start to finish.

This is the wiring layer that turns separate processors into a working chain. You add nodes, say how many audio channels each one carries, connect them, and prepare the whole graph for a chosen sample rate and block size. Then you can render a stretch of sound offline, one block at a time, and get exactly the same result every run. There is no sound card involved and no timing luck: it is a clean, repeatable way to describe a signal path and hear what it produces. That makes it ideal for building effect chains, testing them, and previewing mixes before any hardware is in the picture.

#### sim-lib-audio-graph-live

The engine that runs your effect chain in real time, feeding a sound card without stutters or dropouts.

This is the piece that takes a prepared signal path and runs it live, inside the tight timing window a sound card gives you. It sets up its memory ahead of time so the steady playback path never stops to allocate, which is what keeps audio free of clicks and gaps. Control changes and audio blocks travel through bounded queues, so a slow moment in one part cannot flood the others. It also carries a transport snapshot tied to the stream clock, so playback position stays honest. In short, it is the bridge between a designed chain and the moment-to-moment callback that actually makes sound.

#### sim-lib-plugin-clap

A way to shape a SIM effect so it looks and behaves like a CLAP plugin, and to run CLAP-shaped effects inside SIM.

This crate lets a SIM audio processor wear the CLAP plugin format. By default it works entirely in Rust, with no external SDK and no compiled binary: it builds CLAP-style descriptors that spell out an effect's identity and parameters, and it hosts a SIM processor shaped to that descriptor so it runs in-process. That keeps the whole thing testable on any machine, with no plugin scanning or native hosting required. An optional host feature adds a provider seam for capability-checked loading through an explicit host, so you can extend toward outside CLAP content without pulling an SDK binding into the core.

#### sim-lib-plugin-core

The shared language for describing an audio plugin -- its name, its knobs, and the settings you save and recall.

This is the common ground every plugin format in SIM stands on. It describes a plugin in plain terms: what it is, how many channels it handles, and the list of parameters it exposes. Each parameter carries its range and a default, and it can translate between the plain value a musician reads and the normalized value a host expects. It also holds plugin state, so a patch of settings can be captured, written out, and loaded back exactly as it was. Because it adapts a plugin onto the audio graph node contract, a described plugin can take its place in a signal chain like any other block.

#### sim-lib-plugin-lv2

A way to shape a SIM effect so it looks and behaves like an LV2 plugin, and to run LV2-shaped effects inside SIM.

This crate lets a SIM audio processor take on the LV2 plugin format, the open standard common on Linux. By default it works purely in Rust, with no external SDK and no compiled binary: it builds LV2-style descriptors, complete with the audio and control ports that describe how sound and parameters flow, and hosts a SIM processor shaped to match so it runs in-process. That keeps everything testable without an LV2 development package installed. On Linux, an optional host feature adds a provider seam for capability-checked loading through an explicit host, so you can reach toward outside LV2 content without adding an SDK binding to the core.

#### sim-lib-plugin-vst3

A way to describe a SIM effect in the shape of a VST3 plugin, worked out entirely in Rust with no native binary.

This crate lets a SIM audio processor be laid out in the VST3 plugin format, the standard many studios rely on. It works as a modeled tier: pure Rust, no external SDK, no compiled `.vst3` file. From a SIM effect it produces VST3-style descriptors, including the audio buses that carry sound in and out, and it translates those into the shared plugin description SIM uses everywhere else. Native hosting and binary export are not part of this crate; a scope report spells out plainly what an outside native provider would need. What you get today is a clean, testable way to express an effect in VST3 terms without any SDK or platform hosting in the loop.

#### sim-lib-plugin-wasm

A way to load audio plugins packaged as WebAssembly and run them as ordinary SIM effects.

This crate lets SIM host audio plugins that ship as WebAssembly modules -- small, portable, sandboxed programs that run the same across machines. The default build reads a plugin's manifest and exposes its type surface, so you can inspect what a module offers without pulling in any runtime. Turning on the runtime feature adds a wasmtime-backed host that instantiates the module and runs it as a SIM plugin instance and audio graph node, taking its place in a signal chain like any built-in block. An optional feature also allows a capability-checked fallback that hands loading to an explicit host provider, keeping control over what is allowed to run.

#### sim-lib-stream-alsa

A stand-in for the low-level Linux ALSA sound system that lets SIM audio run and be tested without real hardware.

This crate models ALSA, the direct sound layer beneath most Linux audio, entirely in Rust. It does not touch a real sound card; instead it serves steady, made-up PCM devices that behave predictably every run. It understands the device names Linux users know -- `default`, `hw:` and `plughw:` -- reports what those devices can do, hands back a plan for opening them, and bridges playback into the audio graph while recording captured sound as stream packets. Because there is no real driver and no library to install, an audio project can be built and checked anywhere, and a native adapter can later fill the same model from actual hardware.

#### sim-lib-stream-asio

A stand-in for the Windows ASIO low-latency sound system that lets SIM audio run and be tested without real drivers.

This crate models ASIO, the low-latency driver interface Windows studios rely on, entirely in Rust. It links to no SDK and touches no real driver; instead it serves steady, made-up driver enumeration that behaves the same every run. It reports the ASIO drivers a host would see, hands back a plan for opening a stream, and bridges ASIO-style process callbacks into the audio graph. Because the same graph code can run against this model under Linux testing and against a native driver on Windows, an audio project keeps one code path across very different machines. A native adapter would target Windows and fill the same model from real driver enumeration.

#### sim-lib-stream-coreaudio

A stand-in for Apple's CoreAudio sound system that lets SIM audio run and be tested without a Mac or its frameworks.

This crate models CoreAudio, the sound layer beneath macOS, entirely in Rust. It binds to none of Apple's frameworks and touches no real device; instead it serves steady, made-up PCM devices that behave the same on every run. It presents those devices in the shared stream-host shape SIM uses across backends, and bridges host callbacks into the audio graph so playback and capture flow through the normal path. This exists for native CoreAudio coverage in cases where the portable PortAudio path is not enough, while keeping the build free of Apple hardware and toolkits. It handles sound only; MIDI is left to a separate adapter so this crate stays focused on audio devices.

#### sim-lib-stream-cpal

A cross-platform sound-card connection for SIM, with a hardware-free default lane and an optional path to real devices.

This crate connects SIM audio to cpal, a cross-platform layer that speaks to whatever sound system a machine happens to have. By default it runs a modeled audio site through a shared fake backend, so a project builds and validates with no real sound hardware and no surprises between runs. Turning on the hardware feature adds the native cpal boundary that reaches an actual device on Windows, macOS, or Linux. That native edge is the one place the crate uses low-level buffer handling, and it documents each such step so the risky part stays small, contained, and easy to review.

#### sim-lib-stream-jack

A stand-in for the JACK audio routing system that lets SIM connect and be tested without a running JACK server.

This crate models JACK, the pro-audio routing system that patches sound and MIDI between programs on Linux, entirely in Rust. It links to no library and needs no server; instead it serves a steady, made-up client with routable ports that behave the same every run. It models the JACK client, its audio and MIDI ports, sample-frame transport, and the callback bridge that drives an audio graph. Because none of this depends on a live JACK daemon, an audio project builds and validates anywhere, and a native adapter can later fill the same model from real JACK client and port registration.

#### sim-lib-stream-jack-provider

A registrable JACK sound provider for SIM, modeled by default and hardware-gated when real JACK is available.

This crate packages the JACK sound connection as a registrable provider that a host can add on demand. By default it is pure Rust and registers a steady, modeled JACK-shaped audio site through the shared provider registrar, so a project gains a JACK placement without linking to JACK or opening any hardware. The hardware feature enables the native JACK module for hosts that register the Rust provider entry directly. It is the seam that lets JACK support stay separate and swappable rather than baked in.

#### sim-lib-stream-pipewire

A stand-in for PipeWire, the modern Linux sound server, that lets SIM connect and be tested without a running daemon.

This crate models PipeWire, the sound and media server behind current Linux desktops, entirely in Rust. It binds to no library and needs no running daemon; instead it serves steady, made-up nodes and ports that behave the same every run. It presents provider-reported PipeWire nodes and the visible SIM client ports, folds quantum, sample-rate, and latency details into the shared stream configuration, and bridges made-up process callbacks into the audio graph and its PCM queues. Because none of this leans on a live PipeWire session, an audio project builds and validates anywhere, while native adapters use the same model for real PipeWire registry events.

#### sim-lib-stream-portaudio

A stand-in for PortAudio, the portable sound layer, that lets SIM play and be tested without a PortAudio install.

This crate models PortAudio, a widely used portable sound layer that runs across many operating systems, entirely in Rust. It binds to no library and touches no real device; instead it serves a steady, made-up default output that behaves the same every run. It presents PortAudio devices in the shared stream-host shape SIM uses across backends, bridges host callbacks into the audio graph, and records the backend priority the sound bootstrap follows when choosing a device. Because there is nothing to install and no hardware to open, an audio project builds and validates anywhere, while a native adapter can later fill the same model from a real PortAudio installation.

### sim-auto

#### sim-codec-uds

a safe diagnostic byte-frame reader for automotive UDS and OBD-II data.

It turns small diagnostic byte frames into SIM records that tools can inspect, compare, replay, and encode again. Read-DID requests, OBD-II mode requests, and trouble-code responses all become structured data with explicit status bits instead of opaque byte strings.

#### sim-lib-auto-core

the automotive vocabulary SIM uses to name vehicles, shop lanes, effects, and access rules.

It gives automotive work a shared set of names for modeled vehicles, diagnostics, status bits, service channels, shop capabilities, transport endpoints, and diagnostic sessions. That shared vocabulary makes experiments easier to compare and easier to review because every piece describes the same kind of thing in the same way.

#### sim-lib-auto-diag

a safe diagnostic fabric that lets SIM read modeled vehicle data and replay it exactly.

It gives automotive tools a vehicle-shaped eval target with synthetic ECUs, trouble codes, PID values, freeze frames, and replayable diagnostic answers. A session chooses modeled data, a cassette, or a named local bridge, while capability checks decide which operations can actually run.

#### sim-lib-auto-vehicle

a vehicle identity lookup layer that keeps workshop data sources behind explicit network contracts.

It gives SIM a safe way to turn a plate label or VIN label into the shared vehicle identity used by diagnostics and vendor sites. Modeled records cover tests and examples, while host-owned bridges can stand in for HaynesPro or biluppgifter.se without putting live endpoints or private vehicle data in the crate.

#### sim-lib-auto-vendor

a manifest-driven vendor engine that keeps vehicle-side actions behind explicit proof gates.

It turns an automotive site manifest into a runnable SIM site without linking a proprietary SDK. A modeled bridge answers requests for tests and fixtures, while the same request shape can point at a host bridge outside the crate.

### sim-citizen

#### sim-citizen

The layer that lets a domain's own data types show up as first-class, well-behaved values inside SIM.

A citizen is any value that SIM treats as a proper public thing: it can be read in from text, written back out, checked for correct behavior, and listed in a running system's inventory. This crate holds the shared support that makes a type into a citizen. It records each type in a registry, installs it into a running library and context, runs a conformance check that reads a value in and confirms it comes back out unchanged, compares two values for real meaning rather than surface bytes, and produces both a browse card and a census row so anyone can see what lives in the system. It is the practical machinery that turns a plain Rust type into something SIM can host, list, and trust.

#### sim-citizen-derive

A one-line marker that writes all the wiring needed to make your data type a full SIM value for you.

Making a type into a proper SIM value takes a fair amount of repetitive support: a registry entry, install steps, a conformance check, field handling, and equality comparison. This crate lets you skip writing that by hand. You place a short marker above your type and describe it with a few plain attributes -- its public name, its version, and how its fields behave -- and the marker generates the matching support for you. It also offers a second marker that stamps a type as a deliberate, named exception when it should not be a hosted value at all, so the exemption is explicit and on the record rather than a silent gap.

### sim-codecs

#### sim-codec

It is the shared workshop that lets every SIM format read text or bytes in and write them back out.

This is the common ground that all the other formats stand on. It sets the rules for turning written or stored data into a checked value, and for turning a value back into text or bytes. It also decides where a piece of output is going -- something to run, something to quote, plain data, or a pattern to match against -- so the same value can be written the right way for each setting. Because every other format in this family shares these rules, they all behave alike, guard against oversized or hostile input the same way, and register themselves the same way. You get one dependable foundation instead of a dozen slightly different ones.

#### sim-codec-algol

It lets you read and write values in familiar infix notation, the ordinary style where symbols sit between their operands.

This is the everyday, math-like surface for SIM. It reads text written in the usual style -- values and operators laid out left to right, with the operator in the middle -- and turns it into a checked value the runtime can work with. It knows the ordinary precedence rules, so it groups things the way a reader expects without extra fuss. Going the other way, it writes any value back out in the same readable form, adding parentheses only where they are needed to keep the meaning clear. Because it covers the whole range of values rather than one narrow kind, anything the runtime can hold can travel through this surface and come back unchanged in meaning.

#### sim-codec-binary

It packs any value into a small, tagged stream of bytes and reads it straight back.

This is the compact byte form for SIM values. Instead of readable text, it writes a tight, tagged frame: a short header, a few shared tables that record repeated names once, and a body that lays out the value efficiently. It can also carry the source position of each part, so values that remember where they came from survive the trip. Reading is guarded by strict limits, so a broken or hostile stream is refused rather than followed. This is the form to reach for when size on disk or over the wire matters, or when you want a value stored and recovered exactly. Arbitrary bytes are treated as untrusted data, never as instructions to run.

#### sim-codec-binary-base64

It carries the compact binary form as plain text, so it can travel anywhere only text is allowed.

Some channels only accept plain text -- an email body, a web field, a log line, a config value. This lets the compact binary form ride along on those channels. It takes the same tight byte frame the binary format produces and wraps it as an ordinary run of readable characters, and it unwraps that text back into the exact bytes on the other side. Nothing about the value changes; you simply get a text-safe envelope around it. That means you can drop a full value into a place that would otherwise reject raw bytes, then recover it later without loss. Text that is not a valid envelope is refused rather than guessed at.

#### sim-codec-bitwise

It writes any value in the smallest, most predictable string of bits, the same value always giving the same result.

This is the tightest packing in the family. Where the ordinary binary form works a byte at a time, this one works bit by bit, so no space is wasted rounding up to whole bytes. Lengths and numbers are written using only as many bits as they truly need, and whole numbers of any sign shrink to their bare significant bits. The result is not just small but canonical: one value always produces one exact string of bits, and one string always reads back to one value. That steadiness makes it a natural fit when you want to name or look something up by its content, since identical values always share an identical form. Measured on real data it comes out about forty to fifty percent smaller than the byte format on everyday records and numbers, for a little more packing work; plain text is the one case that gains nothing, so reach for the byte format there. As with the other byte formats, broken input is refused rather than followed.

#### sim-codec-bitwise-base64

It carries the canonical minimal bit-packed form as plain text, so it can travel anywhere only text is allowed.

Some channels only accept plain text -- an email body, a web field, a log line, a config value. This lets the smallest canonical form ride along on those channels. It takes the tight bit-packed frame the bitwise format produces and wraps it as an ordinary run of readable characters, and it unwraps that text back into the exact bytes on the other side. Nothing about the value changes; you simply get a text-safe envelope around it. That means you can drop a full value into a place that would otherwise reject raw bytes, then recover it later without loss. Text that is not a valid envelope is refused rather than guessed at.

#### sim-codec-bridge

It gives SIM, people, and model seats one checked packet format for requests, replies, reviews, and receipts.

BRIDGE makes an exchange inspectable from the first byte. A packet names who speaks, who receives it, what move it makes, what parent move evidence it cites, and what typed parts it carries. This crate reads and writes the strict line form for that packet and checks the book of allowed parts, moves, derived profiles, and warrants before the packet is trusted. The result is a narrow entry point where collaboration messages have stable identity, clear structure, and no hidden side channel.

#### sim-codec-chat

It reads and writes model conversations -- prompts, replies, and events -- in one neutral, provider-independent form.

Conversations with a model come in many shapes: a request you send, the answer that comes back, events along the way, and the record cards that summarize them. This gives all of those a single, tidy text form that does not belong to any one provider. It also understands native provider payloads for OpenAI, Anthropic, Ollama, LM Studio, Lemonade, and OpenAI-compatible local servers, while keeping the saved conversation in the same neutral record. You can capture a whole exchange, store it, move it, or read it later, and it means the same thing regardless of which service produced it. Because the form is consistent, transcripts from different sources line up the same way, so they can be compared, replayed, or archived without special handling for each origin. It keeps the parts of a conversation clearly separated -- who asked, what answered, what happened -- so the record stays legible.

#### sim-codec-compare

the honest scoreboard that tells you when the bit-packed wire format actually beats the plain one, and when it just wastes your time.

A ready-to-run comparison between the two general-purpose SIM wire formats: the byte-oriented one and the bit-packed one. It carries a built-in gallery of sample data shaped like the things a real program stores -- small numbers, big numbers, decimals, names, text, deep trees, wide records, and repeated blocks -- and for each one it reports two plain facts: how many bytes each format takes, and how long each takes to write and read. A single command prints the whole table. A set of built-in checks pins the headline conclusions in place, so if a later change quietly makes the bit-packed format worse, a test fails instead of a promise silently breaking. Here is the shape of a run (size is the packed format against the plain one, so below one is smaller and better; effort is how much longer the packing takes): kind of data size vs plain write effort everyday records 0.6 1.1x lots of small numbers 0.5 1.5x repeated blocks 0.07 (packed) 1.2x plain text 1.0 9x Read left to right that is the whole story: the packed format roughly halves ordinary data for a little more work, shrinks repeated data to a small fraction, and does nothing at all for plain text while costing many times the effort. Run the report yourself for the current numbers on your own machine.

#### sim-codec-config

It turns small SIM configuration files into ordinary runtime maps and writes those maps back as clean text.

SIM libraries often need a few plain settings: enabled helpers, preferred defaults, limits, and load lists. This crate gives those settings a compact text format that decodes into the same map values the rest of the runtime already understands. A library can read its own table, while a launcher can read one shared file that groups many library tables by id.

#### sim-codec-doc

It reads and writes Markdown, Typst, AsciiDoc, and LaTeX as one structured document value.

This treats a document as more than a flat wall of text. It reads Markdown, Typst, AsciiDoc, and LaTeX into one organized value with real parts -- blocks, sections, math, tables, source fragments, and chunks -- that the runtime can hold and hand around. It can write that structure back out through the supported markup formats. Along the way it can split a document into chunks while keeping track of where each piece came from, so a passage always remembers its place in the whole. That makes it easy to pull a document apart for review, search, or processing and still trust the origin of every fragment. It names any loss or preserved raw material instead of pretending everything translated cleanly.

#### sim-codec-json

It reads and writes any value as JSON, so SIM data flows through the world's most common interchange format.

JSON is the shared language of the web and of countless tools, and this brings SIM into it fully. It can write any value the runtime holds as JSON and read it straight back with nothing lost, using a tagged form that keeps every detail exact. When you need to hand data to an outside program that expects plain, ordinary JSON, it also offers a simpler untagged view, plus a compact description of a value's shape. So you get two modes from one place: a faithful round-trip for your own data, and a friendlier surface for talking to systems that were not built for SIM. Either way, values move in and out through a format almost everything already understands.

#### sim-codec-lisp

It reads and writes values in parenthesized s-expression text, the plain nested form where structure is spelled out with brackets.

This is the bracket-and-list surface for SIM. It reads text written as nested parenthesized forms and turns it into a checked value, and it writes any value back out in that same clear, nested style. When it writes, it pays attention to the setting -- whether the value is meant to be run, quoted, kept as plain data, or used as a pattern -- and shapes the text to suit. Because it covers the full range of values rather than one narrow kind, anything the runtime can hold travels through it and comes back with the same meaning. The nested form makes the shape of a value visible right on the page, which is why it doubles as a faithful, readable way to store and inspect data.

#### sim-codec-lua

It gives SIM a bounded Lua chunk reader and writer that keeps source tied to the shared expression graph.

This crate recognizes Lua chunks, preserves the spelling of source-level values, and groups operators with Lua precedence. It covers the statement shapes builders expect in real scripts: local attributes, assignment, conditionals, loops, function declarations, returns, labels, and gotos, while keeping comments and source spans available to located and tree lanes.

#### sim-codec-mcp

It reads and writes the message envelopes of the Model Context Protocol, checking each one is well formed.

The Model Context Protocol is a standard way for tools and models to exchange messages -- requests, notifications, replies, and errors, each wrapped in a JSON-RPC envelope. This reads one such envelope at a time and turns it into a checked value, and writes a value back out as a proper envelope. Its whole job is that envelope: confirming it is complete and correctly shaped, and translating faithfully between the wire message and the runtime's own form. It deliberately leaves the bigger questions -- how a message is routed, how it travels, what it triggers -- to other parts of the system. That narrow focus means you can trust that any envelope passing through has been validated, with mistakes caught at the door.

#### sim-codec-pratt

It gives SIM codecs a shared way to group infix tokens into expression trees.

This crate keeps precedence parsing in one place for text surfaces that use infix operators. A codec supplies its own lexer and operator table, then receives a located expression tree with the same grouping rules, source spans, and resource limits each time. That keeps language-specific crates focused on their syntax while the common parser handles the careful parts of binding, calls, prefixes, postfixes, and nested input.

#### sim-test-support

It is the shared set of helpers the SIM formats use to test that they read and write values correctly.

Every format in this family needs to prove the same thing: that a value written out and read back comes home unchanged. Rather than each one carrying its own copy of that checking machinery, this holds a single shared set of helpers they all draw on. It offers a ready-made practice runtime to test against, a round-trip helper that sends a value out and back and confirms it matches, and small search helpers for inspecting results. Keeping this in one place means the checks stay consistent across every format, and a fix or improvement lands everywhere at once. It is used only while testing, so it never becomes part of anything shipped, and it stays deliberately light so it never tangles the formats it serves.

#### sim-wasm-abi

It is the shared handshake that lets SIM pass values to and from sandboxed WebAssembly modules.

WebAssembly lets code from elsewhere run safely inside a sandbox, and this is the agreed way for SIM and such a module to talk. It defines the exact byte frames that carry values, descriptions, and lists of what a module offers, so both sides read and write them the same way. With that handshake in place, a guest module can be brought in and its offerings surfaced to the runtime as if they were part of it, ready to be called. This handles only the crossing itself -- the framing and the passing of values back and forth -- and leaves what the guest actually does inside its own walls. The result is a clean, well-defined border between the host and any code loaded into the sandbox.

### sim-discrete

#### sim-lib-discrete

one front door to the whole discrete-math family, where you switch on only the parts you need.

This is the single entry point that gathers the discrete-math pieces under one roof. Rather than tracking several separate packages, you reach for this one and turn on exactly the capabilities your task calls for: the shared calculation core, the graph tools, the counting and enumeration helpers, the component-analysis instruments, and the ranking adapters. Anything you leave switched off simply does not come along, so a small job stays small and a large one pulls in only what it truly uses. On top of that gathering, this crate supplies the wiring that lets these tools show up as live operations inside the running SIM system, plus a browsable index so people can find what is on offer.

#### sim-lib-discrete-algebra

one calculation core that answers many discrete-math questions by changing what "add" and "multiply" mean.

This is the shared spine the rest of the family stands on. It lets you treat a grid of numbers as a single object and ask deep questions about it: what can reach what, what is the cheapest way across, how many distinct paths exist. The trick is that all of these are the same computation with a different notion of combining values. Swap in plain counting and you count routes. Swap in "keep the smaller" and you get cheapest connections. Swap in true-or-false and you get pure reachability. Because one engine handles every case, results stay consistent and the same trusted machinery is reused instead of a fresh, separately checked routine for each question.

#### sim-lib-discrete-comb

count and list every way to arrange or choose things, and give each arrangement its own exact number.

This crate answers the everyday "how many ways" questions and then goes further. It counts arrangements, selections, and orderings exactly, with no rounding and no ceiling, so even enormous totals stay precise. When you want the arrangements themselves and not just the tally, it can hand them to you one at a time without building the whole pile in memory. Best of all, it gives every possible arrangement a unique position number and lets you go both directions: name a position and get the exact arrangement, or hand it an arrangement and learn its position. That pairing turns a vast space of possibilities into something you can index, sample, and step through on demand.

#### sim-lib-discrete-graph

model anything as a network of connections and find out how the pieces link, reach, and cost.

Whenever your problem is really a set of things joined by links -- roads between towns, dependencies between tasks, friendships between people -- this crate turns it into a graph you can question. You can walk it to see what is connected to what, check whether the whole thing hangs together or splits into islands, find the cheapest set of links that still joins everything, and trace the shortest route between any two points. Just as useful, many answers arrive with a certificate: a small piece of evidence you can independently re-check to confirm the result is genuinely correct rather than taken on trust.

#### sim-lib-discrete-rank

turn a discrete object into a position and a grade so you can place it, score it, and compare it.

This crate connects the discrete-math family to SIM's ranking machinery. It takes concrete objects -- a set of chosen items, an ordering, a small network, a on-or-off signal, a bundle of flags -- and gives each one a clear place within the full space of possibilities. From there you can measure how far apart two objects are, so "similar" and "very different" become numbers you can act on. It also compiles a grade from an object's own structure: how tightly a network holds together, how heavy its cheapest connecting skeleton is, how spread out its component pattern is. The result is a single, comparable score drawn straight from meaningful traits rather than an arbitrary label.

#### sim-lib-discrete-spectral

break a pattern over on-or-off choices into its building blocks and read how it is really shaped.

When your data is a pattern indexed by yes-or-no combinations -- which switches are on, which features are present -- this crate lets you look at it in a second, revealing way. It rewrites the pattern as a blend of simple underlying components, so you can see which broad tendencies dominate and which fine details barely register. From that view you can measure how concentrated or how spread out a pattern is, combine two patterns by their toggled differences, and roll information up or down across every subset of choices. It moves between the plain view and the component view quickly and exactly, so nothing is approximated away.

### sim-femm

#### sim-lib-femm-assembly

It gathers every small piece of your model into one big system the computer can actually solve.

A finite-element model is chopped into thousands of tiny triangles, each with its own little share of the physics. On its own, each piece knows almost nothing. This step walks the whole meshed model, asks the physics what each element contributes, and stitches those contributions into one connected system that describes the entire object at once. It keeps track of how the pieces overlap and share edges so nothing is double counted and nothing is dropped. The result is the single, complete set of relationships a solver can work through to find the answer everywhere in your model.

#### sim-lib-femm-codec

It writes your model and its results out as readable text and reads them back without losing anything.

A model, its solution, and the fields it produces all need a way to be saved, shared, and inspected. This turns those things into tidy text summaries you can read, store in a file, or send somewhere else, and it reads them straight back into working objects again. The round trip is faithful: what you write out is what you get back, so a saved model rebuilds exactly and a reported result means the same thing tomorrow. It speaks the shared text forms the rest of the system understands, so your finite-element work travels alongside everything else through the same channels.

#### sim-lib-femm-core

It is the shared vocabulary and foundation every other finite-element piece builds on.

Before you can describe a magnet or a heated part, everyone involved has to agree on the basic words: what a physics kind is, how a parameter is named, what an error looks like, and how limits are expressed. This provides that common ground. It holds the shared names, the stable identifiers, the error reporting, and the small building blocks that all the other finite-element libraries reach for. Because these definitions live in one place, every part of the stack means the same thing by the same term, and a model described in one library reads correctly in the next.

#### sim-lib-femm-field

It reads a solved model and tells you the field values anywhere you point.

Once a model is solved, the answer lives spread across the whole shape as a raw solution. This turns that raw result into the field quantities people actually care about: the potential, the flux density, the field strength, and the flow through a region. You can sample those quantities at the spots that matter to you and read them as clear values rather than as internal numbers. It knows how the solution relates to each of these derived pictures, so you ask for the quantity you want and get a faithful reading, wherever in the model you choose to look.

#### sim-lib-femm-fixtures

It is a set of ready-made test problems whose right answers are already known.

Trusting a solver means checking it against problems where the correct answer is not in doubt. This provides a fixed collection of small, carefully chosen finite-element problems, one for each kind of physics the system handles, each paired with a reference result worked out by hand. You can run any of them through the machinery and compare what comes back against the known truth. Because the problems never drift and their answers are pinned, they make a dependable yardstick: if a solve on one of them starts disagreeing with its reference, you know something changed and needs a look.

#### sim-lib-femm-flow

It patiently drives a stubborn, nonlinear model to a settled answer and tells you how it went.

Some models do not give up their answer in one clean step, because the material behaves differently as the field grows and the problem keeps changing under you. This library handles that. It eases the model toward its answer gradually, taking measured steps and letting the solution settle rather than forcing it, until the whole thing stops moving and a real solution is in hand. Along the way it keeps a running record of what happened: how each step went, whether things were calming down, and when convergence was reached. So you get both the settled result and an honest account of the journey to it.

#### sim-lib-femm-function

It turns a whole model into a simple knob-in, answer-out function you can call.

Instead of treating a model as a big thing you set up and run by hand each time, this wraps it as a plain function: you hand it the settings you care about, and it hands back the quantity, field, or full solution you asked for. Ask for a result and, if you want, it also reports how much to trust that result and how the answer would shift as you nudge the settings. That makes a model behave like any other callable value in the system, so you can plug it into searches, sweeps, and tuning loops as easily as calling a formula.

#### sim-lib-femm-geometry

It is where you draw the two-dimensional shape you want to study.

Every simulation starts with a shape, and this is where that shape is described. You lay down points, connect them with straight lines and curved arcs, close off regions, and label the areas so each one can be told what it is made of. It lets you build the cross-section of the object you care about in clear, named terms. When the drawing is complete, it works out the exact coordinates and hands off a clean, concrete outline ready to be divided into a mesh. In short, it is the drawing board that turns your idea of a shape into something the rest of the tools can act on.

#### sim-lib-femm-material

It is where you say what each part is made of and what is pushing on it.

A shape is only half a model; the other half is what fills it and what acts on it. This is where you spell that out. You assign materials to the regions of your drawing, set the conditions along its edges, place the sources that drive the physics, and choose how finely and how thoroughly the model should be handled. It gives you a clear, named way to attach all of that to a shape. With these descriptions in place, an outline stops being an empty picture and becomes a real physical situation the solver can reason about.

#### sim-lib-femm-mesh

It divides your shape into a fine web of triangles and checks the model makes sense first.

A solver cannot work on a smooth shape directly; it needs the shape broken into many small triangles it can handle one at a time. This does that dividing. It takes the assembled model and covers it with a triangular mesh, fine where detail matters and coarser where it does not, so the physics has somewhere to live. Before it meshes, it looks the model over and flags problems: a region with nothing assigned, an edge that does not close, a setting that cannot hold. Catching those early saves you from a solve that would only fail later, or worse, quietly give a wrong answer.

#### sim-lib-femm-ode

It follows your model through time as the world around it keeps changing.

Not every question is a single frozen snapshot. Sometimes a model is tied to something that moves or shifts, and you want to watch how the whole thing evolves as the clock runs. This lets you do that. It treats the model together with the outside state it is coupled to as a system that changes moment to moment, and it steps that system forward through time, working out where everything stands at each instant. You supply the model and how it connects to the changing world, and you get a trace of how the physics unfolds rather than one still image.

#### sim-lib-femm-physics

It holds the actual laws of nature the simulation obeys, one set per kind of problem.

A simulation is only as trustworthy as the physics behind it, and this is where that physics lives. It carries the governing rules for each kind of problem the system handles: magnets and their steady and alternating fields, static electric fields, heat spreading through a part, and steady electric current. For every small piece of the mesh, it says what that piece must satisfy and what is driving it. By keeping each kind of physics stated clearly and separately, it lets the same machinery study very different situations simply by choosing which laws apply. This is the part that makes a result mean something real.

#### sim-lib-femm-post

It turns a finished solve into the real-world numbers you actually wanted to know.

Solving a model produces a mass of internal values before it becomes an answer to your question. This is the step that reads that finished solution and works out the quantities engineers actually ask for: the energy stored, the force on a part, the flow through a region, the inductance, and field readings at the spots you choose. You point it at a solved model and ask for what you need, and it computes those meaningful figures for you. It bridges the gap between a technically complete solve and the practical numbers that let you make a decision about your design.

#### sim-lib-femm-prelude

It switches on the whole finite-element toolkit in a single step.

The finite-element domain is made of many separate libraries, each doing one job. Wiring them all into a working session by hand would be tedious and easy to get wrong. This spares you that. It is one entry point that installs the entire stack at once, along with the number tools underneath it, so that geometry, materials, meshing, physics, solving, and reporting are all present and ready together. You bring in this one thing, and everything you need to describe, solve, and inspect a model is set up for you. It is the light switch that brings the whole room on.

#### sim-lib-femm-query

It keeps every FEMM answer path speaking the same model-query language.

FEMM models can be asked for many kinds of answers: a scalar result, a field, or a full solution. This library holds the shared request shape for those questions and the callable wrapper that resolves model inputs the same way every time. That means the function layer and the sensitivity layer both work from the same payload, the same defaults, and the same query meaning instead of carrying separate copies of the rules.

#### sim-lib-femm-sensitiv

It tells you how much your result would shift if you nudged each design setting.

Knowing the answer to a model is useful; knowing which settings most affect that answer is what lets you improve a design. This works out exactly that. For a chosen result, it reports how sensitive that result is to each of the settings you can control, so you can see which knobs matter and in which direction to turn them. It reaches those sensitivities the most trustworthy way each case allows, and it labels every reading with how it was found, so you always know whether a slope is an exact figure or a careful estimate. You get direction and honesty together.

#### sim-lib-femm-solve

It takes a described model all the way to a solved answer and hands you proof it was done right.

This is the engine that actually produces the answer. Give it a model and it carries the whole job through: it meshes the shape, gathers the pieces into one system, and works that system out to a settled solution. It knows more than one way to crack the system and falls back sensibly when the first path does not suit. Every completed solve comes with a certificate, a short honest record of how it was done, whether it converged, how close it got, and how much to trust it. So you finish not just with a result but with evidence you can check that the result is sound.

#### sim-lib-femm-space

It works out the fine geometric details inside each triangle so the solver knows how values vary across it.

A mesh gives you triangles, but a solver needs more than their corners; it needs to know how a quantity changes as you move across each one and how the pieces knit together into a smooth whole. This supplies that inner machinery. For every element it works out the local shape, how a value is interpreted between the corners, and how steeply it changes from place to place. It also keeps track of which unknowns belong where across the whole model. This is the quiet groundwork that lets the physics be expressed cleanly on top of a plain grid of triangles.

#### sim-lib-femm-tape

It remembers work already done so repeated solves do not start from scratch every time.

Solving a model is real effort, and much of that effort is wasted when you solve the same or a nearly identical model again and again, as happens during a design sweep or when computing how results change. This keeps a memory of the heavy work. It stores the expensive intermediate results and finished solutions, tagged by a fingerprint of the model, its mesh, and its settings, so that when the same situation comes around again it can reuse what it already has instead of redoing it. It keeps that memory to a sensible size, holding on to what is worth keeping and letting go of the rest.

### sim-foundation

#### sim-config

layered SIM settings stay inspectable because every source becomes the same table-shaped data before it is merged.

`sim-config` gives SIM a common base for configuration without inventing a second settings world. Built-in defaults, probed defaults, home files, working-directory files, and explicit overrides all land in one directory of library tables. The merge result carries where each effective field came from, so a loader, command line, report, or agent can show why the current setting has that value.

#### sim-cookbook

The engine behind SIM's built-in lessons that teach each library from the inside.

Learning a system is easiest when the lessons live next to the thing they explain. This crate powers that library-owned teaching lane. A lesson -- a setup file paired with a short note on its purpose -- ships inside the library it teaches. When that library loads, its lessons register themselves, and this engine gathers them into books and chapters that any SIM surface can show: the command line, the web view, the in-product help, or an assistant. It reads and checks each lesson collection, embeds it at build time, keeps a searchable store, works out what to read next, and lets a person layer their own notes on top in a steady, repeatable way. The result is one consistent library of examples drawn from across the whole system.

#### sim-lib-net-core

The quiet reading room that turns raw web traffic into clean, understandable pieces.

When SIM talks to web services, the bytes arriving over the wire are messy: addresses to pick apart, response headers to read, a body whose length is signalled in one of several ways, and streams that dribble in one line or one record at a time. This crate does that careful reading and nothing else. It splits addresses, parses the head of a response, works out how the body is delivered, frames incoming lines even when a line is cut across two arrivals, and decodes the common streaming formats that live services push. It touches no socket, opens no connection, and makes no decisions about what a message means; the caller keeps full control of the network and the meaning, while this crate handles the fiddly framing correctly and the same way every time.

#### sim-lib-surface-card

The shared name-translator that presents SIM's tools cleanly to outside systems and people.

Inside SIM a tool carries a structured name with a group and a dotted path. Outside systems each want that name in their own style: one tool platform allows only letters and underscores, while a human reading a menu wants the natural slashed-and-dotted form. This crate holds the single agreed rule for that translation, so a given SIM name always turns into the same external name for the same audience. It also carries a plain description spine -- a codec-neutral record of what a surface offers -- built only from core types. Concrete surfaces draw their outward names through this one door, which keeps a single source of truth for the naming rules instead of each surface bending them a little differently.

#### sim-macros

A set of labels that let an author declare SIM building blocks in plain Rust and have the wiring written for them.

Adding a new capability to SIM normally means writing a pile of repetitive registration code so the runtime can find and call it. This crate lets an author skip that chore. You mark your items with simple labels -- this is a class, this is a function, this is a constructor, this is a codec, and so on -- and then point one wrapper at the module holding them. The wrapper reads the labels, checks that each declaration is complete and consistent, and generates the connecting code and, when needed, the native bridge for other languages. Mistakes such as a malformed shape or a class missing its constructor are refused right when the code is built, so a broken contract never slips through quietly.

#### sim-table-core

The shared rulebook for naming and requesting table data across SIM.

Many parts of SIM store and fetch data arranged as tables, and they need to agree on two things: which names are allowed for a location, and how a request to read or change a table is spelled out on the wire. This crate is the single home for both. It checks that a path segment is a real, safe name -- not empty, not a sneaky parent escape, not carrying a stray separator -- and it builds a small path step by step, rejecting anything illegal as it grows. It also describes each table request in one agreed form and translates it to and from SIM data using the exact spellings the remote backends already use, so a local store and a distant one understand each other without guesswork.

#### sim-value

A friendly toolkit for building and reading the small data shapes that flow through SIM.

SIM moves information around as compact data forms -- numbers, words, lists, and named fields. On their own those forms are bare and awkward to work with. This crate gives you a tidy, consistent set of helpers for making them and reading them back: build a value, look up a field by name, replace one field while leaving its siblings untouched, or walk into a nested spot by a simple address. Everything is done by copying rather than altering shared state, so a change never surprises code that still holds the older value. One shared home means every part of SIM speaks the same small vocabulary instead of each corner inventing its own.

### sim-kernel

#### sim-kernel

the small, steady center that lets every SIM piece connect.

One dependable place that holds only the shared contracts -- values, expressions, symbols, capabilities, events, libraries, and dispatch records -- so everything else can grow as libraries around it. You get a runtime you can actually keep in your head, where a new codec, number kind, view, or model joins the system without becoming a special case, and where the rules that let those pieces talk to each other are named once, in one place, instead of being re-invented by every part.

### sim-ledger

#### sim-ledger

clear yearly books with exact money values and balance checks at the center.

`sim-ledger` gives SIM a plain model for personal and small-organization accounts: yearly account lists, vouchers, posting lines, and amounts stored as exact hundredths. The pieces are simple enough to inspect directly and strict enough to catch the accounting mistake that matters first, a voucher whose lines do not add back to zero.

#### sim-ledger-cli

a direct terminal path from exported books to checked yearly reports.

`sim-ledger-cli` lets a person create a ledger set, bring in exported books, see which years are present, and print balances without writing a custom importer. It keeps the workflow close to the files on disk, so every step is easy to run again and easy to inspect.

#### sim-ledger-odb

bring LibreOffice Base bookkeeping exports into the ledger model without changing the books by hand.

`sim-ledger-odb` reads the table layout and id counters that LibreOffice Base stores beside a personal ledger, then turns the familiar account, voucher, and posting exports into the shared ledger input format. It keeps the source numbering visible and lets the ledger importer enforce the same balance rules as every other path.

#### sim-lib-ledger-books

a review desk for bookkeeping drafts before they enter the books.

This crate gives ledger workflows a place to check a proposed entry before it is written into a year. It keeps the money exact, makes the supporting references visible, and keeps local tax choices in data so tests and hosts can swap the profile without changing the ledger model.

#### sim-lib-ledger-close

exact year-end statements from local ledger files.

This crate closes a fiscal year without changing the accounting facts. It reads the ledger year, checks that the trial balance nets to zero, groups accounts by their reporting codes, and returns tables that an office workflow can review or export.

### sim-music

#### sim-lib-daw-session

A recording-studio session you can build, arrange, and bounce to audio without opening any studio software.

This gives you a headless workstation session as plain, portable data: tracks, buses, clips, transport position, plugin-chain state, and recording notes all live in one object you can save, share, or hand to a helper. It carries an audio graph patch so the whole arrangement knows how to sound. Because it needs no sound card, it can render an exact offline audio buffer for previews, checks, or review, and the same session always bounces to the same result.

#### sim-lib-midi-ble

A way to find and talk to wireless Bluetooth MIDI controllers, or to rehearse that link from saved fixtures when no adapter is around.

This handles the fiddly parts of Bluetooth Low Energy MIDI: spotting nearby devices, framing the timestamped packets they send, and wiring them in as ordinary MIDI sources and sinks. By default it runs from recorded device fixtures, so discovery can be exercised and checked without a live Bluetooth radio. Turn on the hardware option and it reaches real BlueZ adapters and places wireless endpoints as playable rows in a stream host.

#### sim-lib-midi-core

The shared vocabulary of MIDI -- notes, timing, and control messages -- that every other music tool in SIM speaks.

This is the common ground for MIDI across the whole music stack. It defines tick-based timing, the small bounded numbers MIDI uses for bytes and channels, and the event model covering note messages, meta events, and system-exclusive data. It also gives you in-memory ways to read and write streams of events, a simple note-echo transform, controller-number names, and tempo math. Because everything agrees on these types, higher tools can pass music around without translating between private formats.

#### sim-lib-midi-live

Fast in-and-out buffers that let live MIDI flow through your setup without stalling when things get busy.

This gives you fixed-size ring buffers that sit between incoming real-time MIDI and the tools that consume it. One buffer acts as both a place to write events and a place to read them back in order; another tags each event with the track it belongs to. If a consumer falls behind and a buffer fills, the oldest event is dropped and counted rather than blocking the live input, so a slow reader never freezes a live player.

#### sim-lib-midi-rtmidi

A bridge to the MIDI ports on your computer, with a stand-in mode for testing when no gear is plugged in.

This connects the SIM music stack to the ordinary MIDI ports your operating system exposes through the well-known RtMidi backend. By default it serves predictable fake ports, so you can develop and check MIDI routing with nothing physically attached. Switch on the hardware option and it enumerates real ports and opens them, while the opened streams still behave as the same MIDI sources and sinks the rest of the stack expects, including precise conversion of backend timestamps into tick time.

#### sim-lib-midi-shapes

A tidy text form for MIDI so events, tracks, and whole files can be written down, read back, and handled as first-class objects.

This gives MIDI a readable text skin. Its encode and decode functions round-trip events, channel messages, meta events, system-exclusive data, raw bytes, tracks, and full Standard MIDI Files through a compact bracketed form, reporting any trouble as clear errors. It also wraps each canonical form as a runtime citizen, so a MIDI note or track becomes an object the SIM runtime can hold, name, and reason about, published under a documented set of shape values.

#### sim-lib-midi-smf

Reads and writes ordinary .mid files, the standard way music moves between programs.

This handles the on-disk Standard MIDI File format in both directions. It parses .mid and .smf bytes into an in-memory song model and serialises that model straight back to bytes, reusing the shared MIDI event types. It covers all three file formats, the variable-length timing encoding, running-status compression, and cleaning up or merging tracks. Timing is read in the common ticks-per-quarter form; the rarer SMPTE timing is refused rather than mishandled.

#### sim-lib-midi-sysex

Makes sense of the maker-specific MIDI messages that carry synth patches and tuning tables, turning raw bytes into readable settings.

System-exclusive messages are the private channel where instruments send patches, tunings, and device settings as opaque bytes. This crate reads those payloads as structured, named messages and writes them back. It covers the universal messages every device shares, the MIDI Tuning Standard, and Yamaha's own messages including full DX7 voice and bank patches, with packed and unpacked voice conversion and correct checksums. Every data byte is validated, so bad input is flagged instead of trusted.

#### sim-lib-midi-wasm-frame

Compact, frame-safe descriptions of MIDI data ready to hand across to a browser or plugin boundary.

This packages MIDI into simple, self-contained frames that survive a trip across an interface boundary. Despite the name it does not compile any WebAssembly or ship browser glue; instead it defines the data descriptors that a web or plugin adapter can serialise and pass along, and each event frame round-trips exactly through its byte form. It is the neutral shape MIDI takes when it needs to leave the Rust core and be received elsewhere.

#### sim-lib-music-analysis

Looks at a piece of music and reveals its structure -- what chords are sounding and how the notes move moment to moment.

This studies music material and produces structural views you can read. It turns a piano roll into per-moment frames showing which pitches are sounding, starting, ending, or held over, then segments that timeline into chord-bearing stretches with pitch ranges and pitch-class masks. With its spectral option it adds a Walsh-Hadamard analysis of melodies, contours, and pitch-class windows, giving a different angle on repetition and shape.

#### sim-lib-music-combinators

A shelf of generative players -- arpeggiators, basslines, drum patterns, step sequencers -- that turn simple inputs into steady streams of notes.

This layers reusable players on top of the core music types. Feed each one musical raw material -- chords, scales, drum kits, step lanes -- and it renders a deterministic stream of play events with matching trace data, so the same settings always give the same performance. The collection covers arpeggiation in a couple of flavours, walking basslines, drum patterns including a Euclidean generator, polyphonic step sequencing, and multi-stream note generation, plus friendly builders for assembling the music objects they read.

#### sim-lib-music-core

The heart of the music world in SIM: notes, chords, melodies, and scores, plus the timeline they live on.

This supplies the concrete music domain the rest of the stack works with. It defines the music object model -- notes, chords, melodies, and scores -- along with the piano roll and time grid they sit on, events and lanes, players and playables, performances and takes, an arranger, freeze surfaces, and trace data. It also carries the descriptor metadata that spells out each component's ports and parameters, and registers all of it with the runtime as first-class citizens.

#### sim-lib-music-lift

Raises a plain MIDI file into something richer -- a readable piano roll, a chord progression, or separated voices.

Lifting takes a low-level recording and pulls more meaning out of it. This crate reads a parsed MIDI file and raises it into a structured music view: a piano roll, a moment-by-moment analysis roll, a chord progression, or a counterpoint of separated voices. Each lifter reports back not just the result but diagnostics that explain any lossy or ambiguous choices it had to make, so you can trust what you got and see where it guessed. Convenience entry points make each lift a single call.

#### sim-lib-music-lower

Takes a structured piece of music and renders it back down into a playable MIDI file.

Lowering is the reverse of lifting. This crate takes a structured music object or a full score and turns it into a concrete, playable Standard MIDI File, then serialises that file to bytes ready to save or send. Options let you set the timing resolution, supply a tempo map, and decide how voices are spread across MIDI tracks, so the rendered file lands in the shape a sequencer or player expects.

#### sim-lib-music-notation

Turns a score into readable notation text and reads it back, using a familiar LilyPond-style form.

This is the notation surface for SIM music. It converts between a score -- and related pieces such as melodies, progressions, and counterpoint -- and a text rendering in a subset of the well-known LilyPond notation language. A single codec entry point offers import and export in both plain and diagnostic-carrying forms, so you can move fluidly between a music object and human-writable notation, and it installs as a loadable runtime library for on-demand use.

#### sim-lib-music-shapes

Gives every music object a readable text form and makes it a first-class object the SIM runtime can hold and match.

This applies the SIM shape protocol to the music types. It provides read-and-construct citizen descriptors that round-trip music objects through canonical text forms, a bracketed codec that encodes and decodes every music representation, and a loadable library that registers documented shape values for the music namespace. The codec is the canonical text bridge: encode functions render a music value to its text form, and decode functions parse that text straight back into the matching type.

#### sim-lib-music-synth

A kit of software synthesizers -- from a DX7-style FM engine to modular System 55 and 700 rigs -- that you can play entirely in code.

You get a full bench of playable synth building blocks: oscillators, filters, envelopes, LFOs, modulation routing, and voice allocation for polyphony. On top of those parts sit several recreations of classic instruments, including a Yamaha DX7-style FM voice, a Korg PS-3300-style machine, and the big System 55 and 700 modular systems, each with ready patches and render fixtures. Everything is pure software, so you can dial in a sound, hear it, and reuse it without owning a rack of vintage hardware.

#### sim-lib-music-transform

Reworks musical material with the classic moves -- transpose, invert, reverse, stretch, and compress.

This applies transformations to music. It covers the classic operations a composer reaches for -- transpose, invert, retrograde, augment, and diminish -- plus configurable remaps of pitch and time, pattern mutators, and a gated custom event-filter pipeline for bespoke changes. Each transform reads a music object into a canonical piano roll and returns new music, optionally paired with diagnostics that describe what changed, so edits stay traceable rather than mysterious.

#### sim-lib-music-wasm-frame

Frame-safe descriptions of music objects, ready to carry across to a browser or plugin without dragging the whole engine along.

This packages music into simple frames that travel cleanly across an interface boundary. Despite the name it compiles no WebAssembly and ships no browser glue; it defines frame-safe music descriptors and the stable string names that wasm-engine entrypoints go by, so a browser or plugin adapter has fixed identifiers to bind against. It carries no compiled engine and runs nothing itself -- it is purely the settled shape music takes at the edge.

#### sim-lib-pitch-chord

Builds chords from notes, scale degrees, or jazz symbols, voices them, and can harmonize a melody for you.

This is the chord workshop. It builds chords from raw pitches, from scale degrees, or from jazz-style symbols, then reshapes them with voicing and velocity policies to sit and sound the way you want. Generative players harmonize incoming pitches against a chosen scale, and on top sit a wire-serializable chord-progression sequencer and a roman-numeral-aware harmony suggester that proposes what might come next.

#### sim-lib-pitch-core

The basic alphabet of pitch -- notes, note names, octaves, and the distances between them -- that the rest of the theory tools share.

This defines the foundation pitch types every other pitch crate builds on: the twelve pitch classes counted mod-12, octave-aware pitches, spelled notes with letter and accidental, and intervals measured in semitones. It follows the familiar conventions where C is zero and middle C is MIDI note 60, so the numbers line up with what musicians and MIDI both expect. Higher crates lean on these types instead of inventing their own.

#### sim-lib-pitch-dissonance

Scores how tense or restful a group of notes sounds, from several theoretical points of view at once.

This rates a collection of pitch classes for dissonance against a set of interchangeable models. It offers an interval-vector weighting, a Forte-style complexity measure, a key-relative model that weighs how notes function in a key, and a tritone-density ratio. A registry runs every model at once so you can compare readings, and the whole set installs as a runtime library you can call on demand.

#### sim-lib-pitch-namer

Names a group of notes in every musical language at once -- and translates a name from one school to another.

This is the aggregator over the pitch-naming schools. It defines the shared naming interface and the taxonomy of schools, then drives every built-in one -- Forte set-class names, functional roman numerals, plain prime forms, neo-Riemannian labels, and jazz chord symbols -- through a single registry. That registry can label a set of notes in every school at once and translate a label from one school into another, so a chord can carry many names side by side.

#### sim-lib-pitch-namer-forte

Gives any group of notes its Forte set-class name, the standard label set theory uses.

This implements the Forte naming school. It maps a group of pitch classes to its Forte set-class name -- for instance 4-27 for a dominant seventh -- through a lookup table of prime-form patterns. Before matching, it normalises the set to prime form, so any transposition or rotation of the same shape resolves to one name. The result is a stable, standard label that scholars and analysis tools recognise.

#### sim-lib-pitch-namer-jazz

Reads and recognises jazz chord symbols, turning names like Cmaj7 or Am7/G into chords and back.

This implements the jazz naming school. It parses jazz chord symbols such as Cmaj7 or Am7 over a G bass into a structured symbol, realises them as concrete chords, and works the other way too: given a group of notes it recognises which jazz chord they form by trying every root and quality. It speaks the shorthand working jazz musicians actually write on a chart.

#### sim-lib-pitch-namer-riemann

Labels a triad by its function -- major or minor tonic -- in the neo-Riemannian style.

This implements the Riemannian naming school. It labels a triad by its functional quality relative to its root, telling a major triad from a minor one through case -- an upper-case letter for the major function, a lower-case letter for the minor. It rotates a group of notes so the root sits at zero, matches the major or minor triad pattern, and returns nothing for sets that are not triads, keeping its answers honest.

#### sim-lib-pitch-namer-roman

Reads a chord in the context of a key and names its scale degree -- I, V7, and so on -- the way theory class does.

This implements the functional roman-numeral naming school. Given a key, it labels a chord by its scale degree from one through seven and by its quality, using upper-case numerals for major chords, lower-case for minor, a small circle for diminished, and seventh suffixes -- so a dominant seventh in a major key reads as V7. It needs a key to work against and returns a plain diagnostic when a chord will not fit.

#### sim-lib-pitch-scale

Defines scales and modes and can snap incoming notes onto the scale you choose.

This gives you scales and modes as working objects. It defines the diatonic and symmetric modes, anchors a mode to a tonic to make a concrete scale, and provides the diatonic operations built on them -- degree lookup, moving notes up and down within the scale, and mapping chord tones to scale tones. Performance-oriented players go further, quantizing, filtering, or remapping incoming pitches onto a chosen scale so a part stays in key.

#### sim-lib-pitch-set

Packs a group of pitches into a compact bit pattern and runs the set-theory operations on it fast.

This models unordered groups of pitches as compact bitmasks. A twelve-slot mask packs the pitch classes into a small integer and supports transposition by rotation, inversion, prime-form normalisation, and the interval-vector census that set theory leans on. A wider mask does the same across the full 128-key range. Companion types pair a mask with an optional root and encode chords as stacks of thirds, giving analysis tools a quick, exact representation.

#### sim-lib-pitch-shapes

Gives pitches, scales, chords, and keys a readable text form and makes them objects the SIM runtime can hold.

This is the text and runtime surface for the pitch theory tools. It provides string round-trips for pitches, intervals, pitch-class masks, scales, keys, chords, and chord symbols, wraps each canonical form in a citizen descriptor for read-and-construct evaluation, and exposes the types as SIM shapes through a loadable library. In short, a scale or chord becomes something you can write down, read back exactly, and hand to the runtime as a named object.

#### sim-lib-pitch-wasm-frame

Frame-safe descriptions of pitch data, ready to carry across to a browser or plugin boundary.

This packages pitch data into simple, self-contained frames that survive a trip across an interface boundary. Despite the name it compiles no WebAssembly and ships no browser glue; it defines the data descriptors that a web or plugin adapter can serialise and pass along. It is the neutral shape pitch information takes when it needs to leave the Rust core and be received by some other surface.

#### sim-lib-sound-audio-lift

Listens to raw audio and works out the notes hiding inside it.

This analyses raw recorded audio and lifts it into pitched note candidates. Its analysers -- one tracking spectral peaks, one combing for harmonics -- break the sound into per-window frames and assemble candidate notes under configurable options, so you get a considered guess at what was played rather than just a waveform. With its music option turned on, the results convert straight into piano rolls, diff rolls, and counterpoint you can work with.

#### sim-lib-sound-bridge

Connects MIDI notes to actual sound, deciding which instrument, tuning, and voice each note plays through.

This is the junction between the MIDI world and the sound world. It consumes MIDI events and produces scheduled tones, resolving each note's program through a bank of timbres, its pitch through a tuning, and its polyphony through a pool of voices. Per-channel settings and state let it track and shape behaviour independently on each channel, and it installs as a runtime library so the whole bridge is available on demand.

#### sim-lib-sound-core

The basic building blocks of sound -- frequency, loudness, and the ingredients of a tone.

This defines the foundation acoustic types the whole synthesis layer shares: frequency, amplitude, and phase quantities, and the partial, envelope, and tone models that build a spectral tone out of sinusoidal components. It also includes helpers for sensible default envelopes and for converting equal-temperament pitches to frequencies. These are the small, shared pieces every sound crate assembles into something you can hear.

#### sim-lib-sound-dissonance

Estimates how rough or smooth two or more sounds are together, using established psychoacoustic models.

This scores the sensory roughness of sound using a family of well-known psychoacoustic estimators -- Plomp-Levelt, Sethares, Helmholtz beating, and harmonic entropy. A registry lets you look them up by name and run them, and a runtime surface installs the whole set as a library. Unlike theory-based scoring, these models work from the actual spectral content, so they judge how a combination genuinely sounds to the ear.

#### sim-lib-sound-gm

The standard General MIDI instrument and drum set, so program numbers map to the sounds everyone expects.

This provides the General MIDI sound set. It includes the standard drum map, naming each percussion key and resolving its label, and a mapping of the 128 standard melodic programs onto concrete timbres in a timbre bank. In short, it makes the familiar General MIDI numbering -- where a given program means a particular instrument -- resolve to real sounds the SIM stack can play.

#### sim-lib-sound-render

Turns synthesized tones into real audio samples and writes them out as a WAV file.

This renders tones into playable audio. It takes synthesized tones and produces interleaved PCM samples, rendering single tones and mixing scheduled tones with per-tone timing and panning, then encodes the mix as a standard 16-bit WAV. Options set the sample rate and channel count. It is the step that finally turns a described sound into something a speaker can play or a file can store.

#### sim-lib-sound-shapes

Gives every sound ingredient -- tones, spectra, timbres, tunings -- a readable text form and makes it a runtime object.

This gives the sound layer a text skin. Its encode and decode functions round-trip the sound types -- frequency, amplitude, phase, partial, envelope, tone, spectrum, timbre, filters, tuning descriptors, dissonance models, and the bridge and renderer options -- through their bracketed text forms. Citizen descriptors wrap those forms as first-class objects, and a runtime surface installs the shape definitions as a library, so a timbre or tuning becomes something you can write, read back, and hand to the runtime.

#### sim-lib-sound-spectrum

Breaks a sound into its frequencies and measures its character -- brightness, peaks, and how it changes.

This gives you the frequency-domain view of a sound. It builds a spectrum -- a magnitude picture across frequency -- either from a synthesized tone or from recorded samples, then measures the common descriptors that summarise timbre: the peaks, the spectral centroid that tracks brightness, flatness, rolloff, and flux that tracks change over time. It turns a raw sound into a handful of readable numbers about its character.

#### sim-lib-sound-timbre

A library of instrument voices and the filters that colour them, from pure sines to plucked strings and bells.

This defines timbre -- a named synthesis recipe with a default envelope, descriptive metadata, and a chain of filters. Its recipes cover pure sine, sawtooth, square, and triangle waves, organ pipe, plucked Karplus-Strong strings, FM, and inharmonic bell sounds, and its filter family shapes their spectra. A runtime surface installs the built-in timbre cards as a library, so a set of ready voices is available to play the moment you need them.

#### sim-lib-sound-tuning

A collection of tuning systems, from modern equal temperament to historical temperaments, that decide the exact pitch of every note.

This provides tuning systems and temperaments as interchangeable objects. It includes equal temperament, just intonation, Pythagorean, quarter-comma meantone, Werckmeister III, Young, and arbitrary Scala cents tables, each mapping pitches to and from frequencies. A serialisable descriptor can build any of them, and a runtime surface installs the built-in tuning cards as a library, so switching how an instrument is tuned is a matter of choosing a different system.

#### sim-lib-sound-wasm-frame

Frame-safe descriptions of sound data, ready to carry across to a browser or plugin boundary.

This packages sound information into simple frames that travel cleanly across an interface boundary. Despite the name it compiles no WebAssembly and ships no browser glue; it defines frame-safe sound descriptors and the stable string names that wasm-engine entrypoints go by, so a browser or plugin adapter has fixed identifiers to bind against. It carries no compiled engine and runs nothing itself -- it is the settled shape sound data takes at the edge.

#### sim-lib-stream-bridge

Converts flowing streams between MIDI and audio so one kind of stream can feed the other.

This adapts finite streams of data packets between MIDI and PCM audio, leaning on the existing sound and audio-lifting crates to do the actual conversion. It lets a MIDI stream become an audio stream, or audio become notes, as a step in a pipeline. It deliberately does not talk to host audio or MIDI devices itself; it only reshapes the data as it passes through.

#### sim-lib-stream-file

Reads and writes streams to and from files on disk, with each access recorded and permission-checked.

This provides source and sink adapters backed by the filesystem, so a stream can be fed from a file or written out to one. Every read and write stays behind an explicit file capability and is recorded as a filesystem effect, keeping disk access accountable rather than silent. It reuses the in-tree MIDI file codec for SMF support, and covers WAV audio through the stream audio layer.

#### sim-lib-stream-midi

Wraps live MIDI sources and sinks so they plug into the SIM streaming pipeline as ordinary packets.

This adapts the existing MIDI memory, source, and sink pieces into the stream system's packet form, so MIDI can flow through a streaming pipeline like any other material. It keeps to the shared MIDI contracts rather than adding new device backends, so it works with whatever MIDI plumbing is already in place. It is the connector that lets MIDI join the stream world without changing how MIDI itself behaves.

### sim-numbers

#### sim-lib-numbers-ad

It works out how fast a calculation changes without you ever doing calculus by hand.

When you have a formula and you want to know how sensitive its answer is to each input, this gives you those slopes automatically and exactly. It tracks the rate of change alongside every value as your computation runs, so you get precise derivatives instead of the shaky estimates you would get from nudging numbers and comparing. It handles both quick single-input cases and large calculations with many inputs at once, and it works across the different kinds of numbers the system understands. You write the formula once; the sensitivity information comes along for free.

#### sim-lib-numbers-arith

It lets you add, subtract, multiply, and divide numbers of different kinds together and always get the right answer.

Real work mixes number types: a whole number here, a fraction there, a decimal somewhere else. This handles the everyday operations across all of them so you never have to stop and convert by hand. When you combine two different kinds, it quietly widens both to a shared kind that can hold the result without losing anything, then does the sum. If one of your inputs is a symbol rather than a concrete value, it hands the work to the algebra layer instead of failing. Plus, minus, times, divide, and running totals over a list all just work.

#### sim-lib-numbers-bigint

It handles whole numbers of any size, far beyond what an ordinary calculator can hold.

Ordinary computer numbers have a ceiling; go past it and they quietly wrap around to nonsense. This removes the ceiling entirely. You can multiply enormous values, count things that run into the billions of billions, or work through problems where the numbers keep growing, and every digit stays exact. There is no rounding and no silent overflow. When a result naturally becomes a fraction, it flows smoothly into the exact-fraction world so precision is never dropped along the way. Big whole-number math simply behaves the way a careful person with unlimited paper would expect.

#### sim-lib-numbers-bool

It gives you plain true-and-false values that slot neatly into the rest of the math.

Yes-or-no answers are everywhere: a test passed, a box is checked, a condition held. This treats those true and false values as first-class members of the number family. Because it sits at the very bottom of the ladder of number kinds, a true or false can rise naturally into a whole number or a decimal whenever your calculation calls for it. That means a simple flag can be counted, summed, or averaged without any awkward conversion. You get clean logical values that also cooperate with ordinary arithmetic when you need them to.

#### sim-lib-numbers-cas

It lets you work with math as symbols and formulas, not just crunched-down numbers.

Sometimes you want to keep the x in your equation rather than pin it to a value right away. This gives you that: you can hold expressions in their algebraic form, carry unknowns through a calculation, and tidy them up. It knows the common cleanups, so adding zero disappears, and messy expressions shrink to their simplest equivalent. You can move freely between a symbolic formula and the ordinary values it represents, so nothing is trapped in one world. It is the foundation that lets the system reason about the shape of an equation, not only its final number.

#### sim-lib-numbers-cas-diff

It does calculus on your formulas, finding derivatives and integrals as tidy new expressions.

Give it a formula and ask for the derivative, and it hands back the answer as a clean formula you can read, reuse, and simplify further. It also works the other way, finding integrals symbolically. This is the calculus you remember from school, done automatically and exactly on the algebraic form rather than on approximate numbers. Because the set of rules it follows can be extended, you or the system can teach it how to differentiate new operations, and it will apply them wherever they appear. The result is real, symbolic calculus you can trust rather than a numerical guess.

#### sim-lib-numbers-cas-eval

It takes a symbolic formula and works out its value once you supply what the unknowns stand for.

You hold a formula with names like x and y in it, and eventually you want an answer. This is the part that plugs in the values you provide and computes the result. It can run in two ways: give it every value and it produces a concrete number, or leave some blanks and it keeps those parts symbolic, returning a partly-worked expression instead of complaining. An unknown you never filled in survives as itself rather than causing an error. That flexibility means you can evaluate as much as you know now and finish the rest later.

#### sim-lib-numbers-codec

It is how a new kind of number announces itself so the system knows how to read and write it.

When someone wants to add a fresh kind of number to the system, that new kind needs a way to introduce itself: this is my name, here is how to recognize me when I appear in text, here is how to show me back. This provides the tidy paperwork for that introduction. It builds the small description a number provider hands to the runtime so the runtime can accept the new kind everywhere, reading it from what people type and printing it back out. The registration is uniform, so every number kind joins on equal footing.

#### sim-lib-numbers-complex

It gives you complex numbers, the two-part numbers that engineering and physics rely on.

Some problems, like waves, signals, and rotations, are far easier to describe with numbers that have both a real and an imaginary part. This gives you those complex numbers and the arithmetic that goes with them, so you can add, multiply, and combine them naturally. Just as importantly, ordinary whole numbers, decimals, and fractions can rise into complex form whenever a calculation needs it, so you can freely mix a plain value with a complex one and get a sensible answer. It is the meeting point where the everyday number kinds gain their extra dimension.

#### sim-lib-numbers-core

It is the shared groundwork that lets every kind of number in the system behave consistently.

Every number kind, whether whole numbers, decimals, or fractions, needs the same basic scaffolding: a common way to be recognized when typed, a common way to be shown and browsed, and a shared understanding of how one kind grows into another. This provides that common ground once so each kind does not reinvent it. It carries the master registry of number kinds and the map of how they widen into one another, giving the whole family a single, agreed-upon backbone. The payoff is uniformity: numbers of different kinds all look, read, and promote the same predictable way.

#### sim-lib-numbers-exotic

It represents numbers to unlimited precision by unfolding them only as far as you actually need.

Some numbers, like certain famous constants, have digits that never end. This holds such values in a form that can, in principle, go on forever, yet it only computes the detail you ask for. You can request an ordinary decimal approximation and it will unfold just enough to give you one, without ever pretending the value was finite in the first place. Built-in constants come ready to use. It is a way to keep endlessly-precise real numbers around and draw from them on demand, so accuracy is a dial you turn rather than a limit you hit.

#### sim-lib-numbers-f64

It gives you everyday decimal numbers, the fast, general-purpose values most calculations use.

Most practical math runs on decimal numbers: measurements, averages, prices, physics. This provides the standard double-precision decimals that strike the common balance of wide range, good accuracy, and quick computation. You get the ordinary arithmetic on them, and when a calculation reaches into the complex plane, these decimals rise smoothly into complex form so nothing stalls. This is the workhorse number kind, the one you fall back to when you just need to compute a real-world quantity without fuss. It is dependable, quick, and understood the same way across the entire system.

#### sim-lib-numbers-fixed

It offers whole numbers in specific sizes, so you can match the exact range and storage a task needs.

Not every count needs the same amount of room. Sometimes a small, tightly-bounded number is exactly right; other times you want a wider one. This gives you a whole family of sized whole numbers, both the ones that allow negatives and the ones that only count upward, across a range of widths. You pick the size that fits, and values step up into larger sizes along a clear widening path when a calculation grows. This lets you be deliberate about how much range a number holds, which matters when you care about compact storage or matching an outside format.

#### sim-lib-numbers-float

It provides compact decimal numbers that trade a little accuracy for smaller size and speed.

When you have a great many decimal values and do not need the fullest precision, a lighter decimal kind pays off. This gives you single-precision decimals: half the storage of the standard kind, which means more of them fit in memory and they move faster. You get the ordinary arithmetic on them, and whenever more accuracy is called for, they rise into the fuller decimal kind without any manual step. It is the right choice for large collections of measurements or graphics-style data where being compact matters more than the last few digits.

#### sim-lib-numbers-func

It turns a function itself into a value you can name, pass around, and call whenever you like.

A function, the rule that turns inputs into an output, becomes a thing you can hold in your hand here. You can define one, store it, hand it to another part of your work, and call it later with real inputs to get a result. The rule underneath can be a symbolic formula or a built-in operation, but from the outside it is simply a callable value. You can also ask for its slope, the direction and rate at which its output changes. That makes functions as easy to work with as ordinary numbers.

#### sim-lib-numbers-i64

It provides the standard whole numbers, positive and negative, that most counting and indexing use.

Counting, indexing, tallying, tracking positions: this is the ordinary whole-number kind that handles all of it. It covers a very wide range of positive and negative values and does the everyday arithmetic on them quickly. When a calculation turns a whole number into something that needs a decimal or an exact fraction, it rises smoothly into those kinds so precision is preserved rather than dropped. This is the go-to integer for typical work, the dependable middle ground that is roomy enough for almost any count yet fast and simple to use.

#### sim-lib-numbers-numeric

It solves the hard calculus problems by careful number-crunching when a neat formula is out of reach.

Many real problems have no tidy formula answer: you still need the slope of something, the area under a curve, or how a changing system evolves over time. This computes those by numerical means. It can estimate rates of change, add up areas through integration, and step a system forward through equations that describe motion or growth. Better still, it lets you assemble these into a small pipeline: pair a function with a method and a task, and get back a runnable job you can inspect and execute. Because the underlying methods are interchangeable, you can pick the approach that suits your accuracy and speed needs.

#### sim-lib-numbers-prelude

It switches on the whole math toolkit in a single step, so everything is ready at once.

Rather than turning on each number kind and capability one at a time, this brings the entire standard set to life together. In one move you get the everyday numbers, exact fractions, arbitrary-size whole numbers, complex numbers, symbolic algebra, functions, grids of numbers with their specialized versions, and the numerical solving tools. It is the convenient bundle: install it and the full number stack is loaded and cooperating, with no need to remember which pieces to include or in what order. For most work this is the one thing you reach for to get a complete, working math environment.

#### sim-lib-numbers-quad

It measures the area under a curve and estimates slopes by clever, careful sampling.

When you need the total accumulated by a quantity, the area beneath its curve, this works it out by sampling the curve and adding up the pieces. It offers both steady, evenly-spaced approaches and smarter adaptive ones that spend extra effort only where the curve is tricky, so you get accuracy without wasted work. It also estimates how fast a quantity is changing by comparing values at nearby points. These are the practical tools for integration and slope-finding when the shape is known only by the values it produces, and you can choose the rule that fits your precision and cost.

#### sim-lib-numbers-rational

It keeps fractions exact, so one-third really stays one-third instead of a rounded decimal.

Decimals quietly round fractions, and those tiny errors add up. This keeps fractions as fractions, an exact top number over an exact bottom number, so a third plus a third plus a third is exactly one, not a hair off. It always reduces to lowest terms, and because it is built on unlimited-size whole numbers, the fractions can be as fine or as large as needed with no loss. It moves cleanly between whole numbers and decimals as well, so you can slip into exact mode where precision matters and back out when you just want an approximation.

#### sim-lib-numbers-rk

It follows how a changing system moves over time, step by careful step.

Many things are described not by where they are but by how they change: how fast something cools, how a population grows, how an object swings. Given that description, this traces the actual path forward through time. It advances the system in small increments, and it offers both steady fixed-size steps and adaptive ones that shorten where the motion is delicate and lengthen where it is calm, so you get accuracy where it matters and speed where it does not. The result is a faithful trajectory you can follow from a starting point onward as the system evolves.

#### sim-lib-numbers-stats

It summarizes your data with averages, spreads, probabilities, and fairness checks.

Point it at a set of numbers and it tells you the story they hold: the typical value, how spread out they are, and the shape of their likelihood. It covers the common descriptive summaries and probability helpers you reach for when making sense of data. It also computes fairness measures that flag when outcomes fall unevenly across groups. What sets it apart is that these results come with their evidence attached: a computed metric carries the inputs and reasoning behind it as inspectable data, so you can see not just the number but why it came out that way.

#### sim-lib-numbers-tensor

It gives you grids of numbers, from simple lists to multi-dimensional blocks, as one kind of value.

Lots of real data comes in arrangements: a row of readings, a table of figures, an image made of pixels, a stack of layers. This gives you a single, uniform way to hold any such arrangement of numbers, from a plain list up to a many-dimensioned block, and to build them with simple constructors for vectors, matrices, and beyond. Because the shape is part of the value, everything that works on grids works the same regardless of how many dimensions you use. It is the common container that turns scattered numbers into structured data you can operate on as a whole.

#### sim-lib-numbers-tensor-bcast

It lets you combine grids of different shapes sensibly, stretching the smaller to match the larger.

Often you want to apply one small thing across a big one: add a single number to every cell, or combine a short row with each row of a table. This handles those combinations by the familiar broadcasting rules, matching up shapes and stretching where it makes sense so the operation just works. It applies math across grids cell by cell, whether both sides are full grids or one is a lone value spread over the whole. The upshot is that you write the natural operation and it figures out how the shapes should line up, sparing you manual reshaping and looping.

#### sim-lib-numbers-tensor-bit

It stores big grids of yes-or-no values tightly packed and combines them with logical operations.

When you have a large grid where every cell is simply on or off, storing each as a full number wastes room. This packs those true-or-false cells together so they take very little space, then lets you combine whole grids with the everyday logical operations: keep where both are on, keep where either is on, keep where they differ. It is built for masks, flags, and membership grids where the answer per cell is binary. If two grids do not have matching shapes, it refuses rather than quietly producing a misaligned result, so mistakes surface instead of hiding.

#### sim-lib-numbers-tensor-cmplxf

It holds grids of complex numbers efficiently, for signal and wave work done in bulk.

Fields like signal processing and physics work with whole arrays of complex numbers, each having a real and an imaginary part. This provides a grid specialized to carry exactly those two-part values compactly and to operate on them as a unit. Instead of scattering the pairs loosely, it keeps them in a tight, ordered arrangement suited to fast bulk work, and it converts cleanly to and from the system's general grid form so it stays fully compatible. If the number of values does not match the declared shape, it refuses rather than guess, so your data stays trustworthy.

#### sim-lib-numbers-tensor-f64

It gives you fast grids of ordinary decimal numbers, the common case for number-heavy work.

Most grid math, from data analysis to simulation, runs on plain decimal numbers. This provides a grid specialized to hold those decimals in a single tight, contiguous block and to run math across them at speed. Because the values sit together in memory rather than scattered, operations sweep through them quickly. It converts cleanly to and from the system's general grid form, so this fast version and the uniform one use the same interface. If the number of values you supply does not fit the shape you declared, it declines rather than proceed with mismatched data, keeping results sound.

#### sim-lib-numbers-tensor-i64

It gives you fast grids of whole numbers that never overflow into wrong answers.

For grids of counts and whole-number data, this gives you a compact, quick specialization that keeps the values in one tight block for speed. Its standout trait is safety: ordinary computer whole numbers can silently wrap around when they get too big, but this watches for that. As long as everything stays in range, it runs on the fast path; the moment a value would overflow, it widens the whole grid into unlimited-size whole numbers so no digit is ever lost. You get the speed of fixed-size integers for the common case and the correctness of unlimited ones exactly when it matters.

#### sim-lib-numbers-tensor-linalg

It does the matrix and vector math behind graphics, data science, and engineering.

This is the toolkit of classic linear-algebra operations that so many fields quietly rely on. You can multiply matrices, take dot and cross products, flip a matrix on its diagonal, find its determinant, compute its inverse, sum its diagonal, and measure the length of a vector. It also gives you quick ways to build common starting grids: an identity, an all-zeros, or an all-ones grid of the size you name. Together these are the moves behind transforming shapes in graphics, solving systems of equations, and reducing data. You get the standard vocabulary of matrix math ready to apply.

#### sim-lib-numbers-tensor-rat64

It gives you grids of exact fractions, so array math avoids rounding entirely.

When you need a whole grid of values to stay exact, decimals will not do; they round. This provides a grid where every cell is a precise fraction, a top number over a bottom number, kept compact for speed. Each cell is automatically reduced to lowest terms with a tidy, consistent sign, so equal fractions look the same and comparisons behave. It converts cleanly to and from the system's general grid form, staying fully compatible with the rest of the stack. If the count of values does not match the shape you declared, it refuses rather than proceed with mismatched data.

### sim-office

#### sim-codec-mspdi

project schedules can cross the Microsoft Project XML boundary with clear loss reporting.

`sim-codec-mspdi` gives the office family a file exchange path for local Gantt plans. It reads and writes the schedule pieces people need to inspect first: task ids, names, dates, progress, and dependency links.

#### sim-codec-odf

LibreOffice files can carry local office documents without hiding what falls outside the portable model.

`sim-codec-odf` gives the office family local file boundaries for spreadsheets and slide decks. It creates ordinary ODF packages, reads them back into SIM documents, preserves exact sheet values, and keeps slide structure visible as portable document content.

#### sim-codec-ooxml

Office file packages can move through SIM without hiding what the portable model cannot keep.

`sim-codec-ooxml` gives the office family local file boundaries for spreadsheet and presentation documents. It creates ordinary workbook and slide packages, reads them back into SIM documents, and calls out styling, merged cells, transitions, or media that do not fit the portable local models.

#### sim-lib-deck

presentation content stays portable before it enters a slide file or hosted editor.

`sim-lib-deck` gives the office family a compact presentation model with slide titles, narrative bullets, tables, and external image references. A local deck can be inspected, transformed, archived, or exported through the same document boundary as the rest of the suite.

#### sim-lib-doc-core

the small document spine that office codecs, stores, views, and sites share.

`sim-lib-doc-core` gives every office layer the same basic record: what kind of document this is, which stable id names it, what runtime value carries its body, and which outside file or service record it came from. It also gives callers a shape value for a document kind, so selection and validation can stay open instead of depending on a closed list inside the kernel.

#### sim-lib-doc-ledger

a careful handoff from office evidence to accounting reviews.

This crate lets an office workflow review a bookkeeping entry or year-end statement before it touches the books or leaves the local review surface. A message, SharePoint file, task, or issue can support the entry as a reference, while ledger checks supply exact preview data.

#### sim-lib-doc-markup

article files enter the office document flow through the same markup body.

`sim-lib-doc-markup` lets Markdown, Typst, AsciiDoc, and LaTeX articles cross the office file boundary as ordinary article documents. The shared markup body stays portable, so one imported article can be exported through another supported markup format without leaving the office document contract.

#### sim-lib-doc-site

the office bridge that makes external document places loadable without making them the frontend.

This crate gives office integrations one place to register file services, helper processes, and modeled service doubles as document places. A caller can ask for data or preview a write through the same boundary, while the registered place carries its document kinds and required capabilities.

#### sim-lib-doc-store

a local office document cache that keeps edits tied to the ledger that produced them.

This crate gives office work a durable local place to remember document snapshots and the edit projections that came from committed ledger entries. It is useful for offline viewing, undo previews, and tests that need repeatable document state without calling a hosted service.

#### sim-lib-doc-surface

a suite-facing document surface that turns office records into renderable panes and checked edits.

This crate gives office documents a shared scene for screens, decks, tables, and embedded document panes. It makes document previews visible through the existing view stack and turns user intent into clear edit records that a host can inspect before it commits anything.

#### sim-lib-gantt

local project schedules that can be checked and reopened without a vendor system.

This crate gives office work a durable Gantt plan model: tasks, dates, dependency links, progress, and a local database for reopening the same plan later. It also identifies the zero-slack tasks that control the schedule, using the shared graph toolkit instead of a private dependency engine.

#### sim-lib-mail

mail and calendar records stay useful without carrying private bodies around.

`sim-lib-mail` gives the office family a compact shape for messages, events, body previews, attendees, and attachment references. A mailbox item can be linked, reviewed, archived, or projected without turning the message body into ambient data.

#### sim-lib-office-pack

It packages a closed ledger year into review-ready office exports without sending anything live.

Annual statements become a coordinated pack: a spreadsheet, a presentation, a mail draft preview, and an archive preview. The package is built from exact ledger statement values, so the numbers in every output stay tied to the closed year.

#### sim-lib-sheet

spreadsheets keep exact local values before any vendor file format enters.

`sim-lib-sheet` gives the office family a small spreadsheet model with sparse cells, exact rational numbers, formulas, and document projection. A local sheet can be inspected and edited as SIM data before Excel, LibreOffice, or service placements appear.

#### sim-site-dalux

Dalux project items become local SIM office records behind API identity gates.

This crate gives construction project data a Dalux boundary that reads items into local office documents and keeps live service access behind a bearer token from an API identity. It gives hosts a small, named place to connect Dalux without changing the document model.

#### sim-site-libreoffice

LibreOffice automation stays optional, permissioned, and outside the runtime process.

`sim-site-libreoffice` gives the office family a helper-process boundary for LibreOffice tasks such as opening a document and exporting a PDF. It keeps UNO automation behind a small command protocol while the ordinary ODF file codec remains the local default.

#### sim-site-msgraph

Microsoft Graph documents can enter SIM through a modeled-first office site.

This crate gives the office family a Microsoft Graph boundary that works with stable recorded answers by default and requires deliberate host permission for live service reads. It keeps the vendor connection outside the kernel while still fitting the shared document site shape.

#### sim-site-powerproject

Powerproject and Project for the web become permissioned places for SIM Gantt plans.

This crate gives schedule work a vendor boundary without changing the local plan model. It names Powerproject as a live desktop placement, names Project for the web as a Dataverse placement, and keeps both paths tied to the same task and dependency records.

#### sim-site-sharepoint

SharePoint lists and drive folders become reviewable SIM office records.

This crate turns SharePoint list rows into local sheet documents and drive children into external references that keep their web links and ETags. A host can read the Graph response, inspect the shape, and decide what to do before any write is attempted.

### sim-run

#### sim-lib-repl

The interactive prompt where you type a line and SIM answers back.

This is the loadable back-and-forth prompt for SIM. You type one line, the system reads it, works it out, and prints the answer, then waits for your next line. It is the hands-on way to explore, try an idea, and see the result right away without setting up a whole program first. The prompt keeps a clear read-then-answer rhythm and stays out of your way. It does not carry a language surface or number handling of its own; instead it expects your session to already have those brought in, so the very same prompt works over whichever surface you loaded. That keeps it honest and small: it drives the conversation and lets the loaded pieces supply the actual meaning of each line you enter.

#### sim-run

The `sim` program you launch from a terminal to start a SIM session.

This is the small starting program that turns the SIM system on. You run one command, `sim`, and it reads the options you type, then hands control to whatever behavior you asked for. The program itself stays thin on purpose: it bakes in no language surface and no built-in tricks. It simply understands how to bring a library to life and pass your request along. You choose what gets loaded from the outside, so the same starting program serves many jobs. It stays quiet and honest: when you ask for something it cannot find, it tells you plainly instead of guessing. Think of it as the front door to everything else in the system.

#### sim-run-core

The part that reads your command line and sets up the SIM session.

This is the reasoning behind the starting program. When you type a command, this piece figures out what you meant: which language surface to speak, which extra libraries you want, and where the payload of your request begins. It keeps your handoff details safe, chooses the right first library to bring in, and then passes your whole request across to that library. It also turns the result back into a simple yes-or-no exit signal your shell can read. If you point it at a file, it loads from there. If you seed a local store ahead of time, it can find pieces without ever reaching out over a wire. Nothing is assumed for you; every source is one you named.

#### sim-run-loaders

The pieces that let SIM pull in source files, packs, and outside plug-ins.

This is the set of loading mechanisms the starting program can switch on when you want to bring behavior in from outside the base build. It handles readable source files, compact library packs, compiled plug-ins built for your machine, and portable bundles that run the same way anywhere. Each path gives the command surface a consistent route from an artifact to registered behavior inside a running session. These loaders stay small and low-level on purpose, so the front door can add just the loading style you need without dragging in the whole system. When a loaded plug-in offers a placement point, this layer records it as an opaque item the rest of the system can pick up.

#### sim-view-tty

The library that draws SIM in your terminal and reads your keystrokes.

This is the terminal face of SIM. It takes a scene the system wants to show and paints it as plain text that fits your terminal, and it turns the keys you press into clear intentions the system can act on. Both directions are steady and predictable, so what you see and what you type behave the same way every run. It offers two settings: a keyboard-only plain view for a simple terminal, and a richer view that also understands pointer input and a wider palette. The terminal is treated as one kind of display among several, not a special built-in mode, so the starting program stays a plain front door while this piece handles everything about showing and reading in text.

### sim-runtime

#### sim-lib-binding

It keeps track of what every name in a program stands for, and exactly where that meaning holds.

This library is the part of SIM that remembers which value each name points to as a program runs. It supports names that stay put inside the block that created them, names whose meaning can be swapped for the length of a call and then restored, and names defined together so they can refer to each other. When you read a name, you get the right value for the place you are standing in the code. When a temporary setting ends, the earlier one comes back on its own, so surprises stay rare and behavior stays predictable.

#### sim-lib-control

It manages how a running program moves -- pausing, resuming, retrying, and recovering when something goes wrong.

This library shapes the flow of work inside SIM. It lets a computation pause and pick up later, hand values back and forth as it goes, explore several possibilities and back out of the ones that fail, and jump straight out of deep nesting when that is the clearest thing to do. It also handles trouble in an orderly way, offering named ways to recover instead of simply stopping. Together these turn awkward control situations -- long-running steps, search, cleanup, and error handling -- into ordinary, describable pieces you can reason about.

#### sim-lib-core

It is the shared plumbing every SIM library uses to announce what it offers and get it installed once, cleanly.

This library is the quiet foundation the other libraries stand on. When a library wants to publish the values and behaviors it provides, it describes them as plain data and hands that description here. This crate installs those entries into the shared registry a single time, and doing it again changes nothing, so repeated setup never piles up duplicates or half-finished state. Because every library declares its offerings the same way, the whole collection stays consistent, easy to inspect, and easy to combine without each one reinventing the same bookkeeping.

#### sim-lib-dispatch

It picks the right version of an operation based on the kinds of things you hand it.

This library lets one named operation have many implementations and choose the fitting one automatically. You describe several versions of an operation, each meant for a particular kind of value, and when the operation is called this crate looks at the actual arguments and runs the version that matches best. When more than one version could apply, it settles ties in a clear, stated order rather than by chance. The result is that you can add new behavior for new kinds of data without editing the places that already call the operation, keeping code open to growth.

#### sim-lib-exec

It lets a trusted host run a specific outside process with clear permission and tight limits.

Some useful work belongs outside the runtime: a formatter, a compiler, a small command-line helper, or another tool the host already trusts. This crate gives that work a narrow gate. The caller names the exact program and arguments, the host checks permission first, and the run is bounded by a working directory root, a timeout, and a byte limit on captured output.

#### sim-lib-lang-cl

It lets you write for SIM in familiar Common Lisp style, with the parentheses and forms Lisp people expect.

This library gives SIM a Common Lisp face. If you are comfortable with the Common Lisp way of writing -- its list forms, its naming habits, its long-standing conventions -- you can express your ideas that way and have them run on SIM. It is a front for reading and writing in that style, not a separate interpreter hiding inside; the actual meaning is carried by SIM's shared expression graph beneath. So you keep the notation you know while everything you write joins the same runtime that every other SIM surface shares.

#### sim-lib-lang-clojure

It lets you write for SIM in Clojure style, using EDN data notation and an immutable, functional feel.

This library gives SIM a Clojure face. You can use the EDN data notation and the functional, data-first habits that Clojure programmers favor -- leaning on values that do not change and on plain data as the main shape of a program. It is a front for reading and writing in that style rather than a separate engine of its own; the meaning of what you write is carried by SIM's shared expression graph underneath. You keep the notation and the mindset you like while your code runs on the same runtime as every other SIM surface.

#### sim-lib-lang-genconf

It generates a steady, repeatable set of test inputs for confirming that language surfaces behave correctly.

This library builds the raw material for checking that SIM's language surfaces do what they should. It walks the space of possible expressions in a fixed, orderly way and produces inputs that the conformance checks then feed through each surface. Because the walk is deterministic, the same inputs come out every time, so a result today can be compared against a result later with confidence that only the system changed, not the test set. It concentrates the tricky job of producing thorough, reproducible examples in one place, keeping the checks themselves simple.

#### sim-lib-lang-islisp

It lets you write for SIM in ISLISP, the small standardized Lisp with a deliberately compact core.

This library gives SIM an ISLISP face. ISLISP is a trim, standardized member of the Lisp family, built around a small and clearly defined core rather than a sprawling set of features. Writing in this profile means working with that compact, dependable vocabulary, which many people value for its clarity and its stable definition. It is a front for reading and writing in that style, not a separate interpreter tucked away; the meaning is carried by SIM's shared expression graph beneath. You get the tidy ISLISP notation while joining the same runtime as every other SIM surface.

#### sim-lib-lang-julia

It lets you write for SIM in Julia style, the notation favored for technical and numerical work.

This library gives SIM a Julia face. Julia's notation is popular with people doing calculation-heavy and scientific work, and this profile lets you express your ideas in that familiar shape and run them on SIM. It is a front for reading and writing in the Julia style, not a separate engine copied inside; the meaning of what you write is carried by SIM's shared expression graph underneath. So you keep the clean, math-friendly look you already know while your code joins the same runtime that every other SIM surface shares, side by side with them.

#### sim-lib-lang-lua

It lets you write for SIM in Lua style, the small, approachable scripting notation many people already know.

This library gives SIM a Lua face. Lua is known for being small, easy to pick up, and pleasant for scripting, and this profile lets you write in that light, readable style and have it run on SIM. It is a front for reading and writing in the Lua manner, not a separate interpreter carried along inside; the meaning is held by SIM's shared expression graph underneath. You get the gentle learning curve and clean look Lua is loved for, while what you write joins the same runtime that every other SIM surface uses.

#### sim-lib-lang-matrix

It gathers every language surface and checks them all against one shared standard so they agree.

This library is the meeting point where SIM's language surfaces are held to a common bar. It assembles the surfaces together and runs them against a shared set of checks, so you can see at a glance whether each one reads and evaluates inputs the way it is meant to. When the surfaces all pass through the same examples, differences between them stand out plainly and agreement is confirmed rather than assumed. It gives the project one place to answer the question "do all our language fronts still behave consistently."

#### sim-lib-lang-prolog

It lets you write for SIM in Prolog style, stating facts and rules and letting the system find the answers.

This library gives SIM a Prolog face. In the Prolog way of working you do not spell out steps; you state what is true and what follows from what, then ask a question and let the system search for every set of values that fits. This profile brings that declarative style to SIM and connects it to the shared reasoning engine, so your rules and queries run alongside everything else. You get the familiar Prolog feel -- facts, rules, and questions with blanks to fill -- resting on a common foundation instead of a separate tool.

#### sim-lib-lang-ruby

It lets you write for SIM in an expressive Ruby style, with the readable, block-friendly flavor Ruby is known for.

This library gives SIM a Ruby-flavored face. Ruby is prized for reading almost like plain description and for its comfortable use of blocks, and this profile brings that expressive feel to SIM as a small language surface. You can shape your ideas in that fluent style and have them run on the same runtime as everything else. It is a front for reading and writing in the Ruby manner, not a separate interpreter hidden inside; the meaning is carried by SIM's shared expression graph beneath, so the pleasant notation sits on a common foundation.

#### sim-lib-lang-scheme

It lets you write for SIM in Scheme, the small, clean Lisp dialect of the R7RS-small standard.

This library gives SIM a Scheme face, following the R7RS-small standard. Scheme is admired for being minimal and clear, giving you a small set of well-chosen forms rather than a crowded feature list, and this profile brings that tidy style to SIM. You can write in the familiar Scheme shape and have it run on the shared runtime. It is a front for reading and writing in that style, not a separate interpreter tucked inside; the meaning is carried by SIM's shared expression graph underneath, so the clean notation rests on a common foundation.

#### sim-lib-lang-typed-lazy

It lets you write for SIM in a typed, lazy style where values are checked ahead and computed only when needed.

This library gives SIM a typed, lazily-evaluated face. Here the kinds of your values are checked before the program runs, so many mistakes are caught early as clear messages rather than surprises during a run. And work is put off until its result is actually wanted, which lets you describe long or open-ended computations and still pay only for the parts you use. This profile brings that careful, on-demand style to SIM as a small language surface. It is a front for reading and writing in that manner, with the meaning carried by SIM's shared expression graph beneath.

#### sim-lib-logic

It lets you state facts and rules, then ask questions and get every answer that fits.

This library brings rule-based reasoning to SIM. You record facts and the rules that connect them, then pose a question with blanks in it, and the engine finds the values that make the question true. It works by matching shapes against each other and filling in the blanks consistently, and it can hold extra conditions that the answers must also satisfy. Results arrive as a stream you can take from one at a time, so a question with many answers stays manageable. It turns "what combinations satisfy all of this" into a direct thing you can ask.

#### sim-lib-mutation

It lets programs change data in place while keeping every change tracked and permitted.

Most of SIM favors values that do not change, but real programs sometimes need a spot they can update. This library provides those spots -- single-value cells, small holders, growable vectors, and lookup tables -- and every write to them passes through one guarded gate. That gate checks permission and records the change, so in-place edits stay auditable instead of happening in the shadows. You get the convenience of mutable state where it genuinely helps, without giving up the ability to see what changed, when, and under whose authority.

#### sim-lib-namespace

It organizes names into separate modules so large programs do not trip over each other.

As a program grows, many parts want to use short, natural names, and those names start to collide. This library keeps them apart. It lets each area of code hold its own set of names, decide which ones to share, and pull in names from elsewhere on clear terms. You can bring in another module's names as they are, rename them to avoid a clash, or deliberately shadow one with your own. Because the rules for importing, exporting, and renaming are explicit, you always know where a given name came from and what it refers to.

#### sim-lib-pattern

It takes data apart by its shape and handles each case, warning you when a case is missed.

This library lets you describe the shapes your data can take and then respond to each one directly. Instead of poking at a value piece by piece, you write out the forms it might have and let the match pull the parts you care about into named pieces for you. You can define your own kinds of structured values with clearly listed variants, and when you handle them the checker tells you if you have left a possibility unaddressed. That gap-catching turns a common class of quiet bugs into a plain, up-front message.

#### sim-lib-sequence

It works with collections of items -- even endless ones -- without copying them over and over.

This library is SIM's toolkit for series of values. It offers sequences that produce their items only as far as you actually read, so you can describe something long or even unending and still take just the first few. It offers collections that share their structure when you make a changed copy, so building a new version stays cheap instead of duplicating everything. And it offers pipelines that describe a chain of steps -- filter, map, combine -- once and apply them efficiently across a run. Together they let you shape and move data smoothly with little waste.

#### sim-lib-standard-core

It is the batteries-included default bundle that makes SIM useful the moment it starts.

This library gathers the everyday behaviors most people expect a working system to already have. It sets up the permissions and claims that say who may do what, provides ways to compare two values and measure how faithfully one form was turned into another, and includes the harness that checks the system is behaving to standard. It brings the reading and construction of values from text, the Lisp surface for writing them, and the support that lets several language profiles share one core. In short, it wires the pieces together into a distribution you can pick up and use.

### sim-sdk

#### sim-conformance

the runnable checklist that proves SIM actually behaves the way its architecture promises.

This is the executable test suite that holds the whole runtime to its stated contract. Every big claim SIM makes about itself becomes a check you can run: that codecs faithfully round-trip every expression, that classes act as callable functions, that number parsing and promotion can be swapped out, that reading input never quietly runs code unless a host allows it, that named evaluation strategies work, that libraries can be installed and cleanly removed, that a boot receipt replays the same way, and that placement across machines behaves. It exercises the public entry crate exactly as an outside developer would, so the promises are tested through the same door you use.

#### sim-nest

the single starting point a developer adds to reach every part of the SIM runtime.

This is the one-stop crate you depend on to work with SIM. Instead of hunting down and wiring together the kernel, the codecs, the number domains, the list and table backends, and the behavior libraries one by one, you add this single package and get them all through a tidy set of named modules. It ships the installer that boots a working runtime and the authoring helpers for writing functions, classes, macros, and shapes. You pick how much of the system you want through named feature groups, starting from a small default and widening as your needs grow. It is the front door: the place newcomers begin and the surface everything else hangs behind.

### sim-shape

#### sim-shape

it is the single component that decides whether a piece of data fits a described pattern, and tells you exactly what it found inside.

sim-shape gives SIM one shared way to describe the form a value should take and then check any value against that description. A shape can say "any number", "exactly this word", "a list of these", or a named class, and it can be combined with and, or, and not to build richer descriptions. When a value is checked, the shape does two jobs at once: it reports whether the value matches, and it captures the interesting parts by name so the rest of the system can use them. The same descriptions also compare against each other, so you can tell when one pattern is stricter than another. Because one engine does all this, matching stays consistent everywhere it is used.

### sim-storage

#### sim-list-cell

A classic linked-list store that holds items in order so a program can keep and change sequences.

This is the everyday list keeper for SIM. It stores a run of items one after another, each cell pointing to the next, so the order you put things in is the order you get them back. Because cells can be shared, two lists can start from the same tail without copying every item, which keeps memory small when many lists overlap. You can build a list, walk it from front to back, and change what it holds while the program runs. It plugs into SIM as a loadable part, so the runtime picks it up only when a program actually asks for ordered lists.

#### sim-list-lazy

A list that figures out its contents only when you ask, so huge or endless sequences cost little until read.

This backend holds lists that stay unread until someone looks at them. Each step computes its own item and the rest of the list on demand, so a sequence can be enormous, or even without a fixed end, while only the parts you touch are ever worked out. It can also wrap a running source of values, turning a stream into a list you read one item at a time. Work is done as late as possible and no sooner, which saves effort when a program peeks at only the first few results. It loads into SIM as an optional part, present when a program wants deferred sequences.

#### sim-table-db

A file-cabinet style store that keeps named values in a tree of folders you reach by path.

This backend arranges named values as a directory tree, the way folders hold files on a computer. Each value has a name, and folders can hold more folders, so you reach a value by walking a path from the top. Reading and writing pass through permission checks, so a program only touches the parts it has been allowed to touch. It behaves both as a table of names and as a browsable tree, which suits settings, records, and anything that reads better when grouped and nested. It joins SIM as a loadable part, added when a program needs path-addressed storage under access control.

#### sim-table-fs

Turns a folder on disk into a lookup table where each entry is a file and each subfolder is a nested table.

This exposes a host directory as a SIM table: every table key maps to a file, and nested tables map to subdirectories, so a folder tree becomes a structured store you can read and write by key. Access is gated by the kernel's table capabilities and passes through the configured codec. With its format options enabled, recognised extensions -- for example MIDI, music, tone, and tuning files -- round-trip automatically through their domain shapes.

#### sim-table-hash

A quick name-to-value lookup store that finds any entry by its key almost instantly.

This is the plain, fast lookup table for SIM. It keeps entries in memory, each under a symbol key, and finds, adds, or removes one by its name without scanning the rest. Because it uses a hash map underneath, the time to reach an entry stays about the same whether the table holds a handful of names or many thousands. It is the sensible default when a program just needs to associate names with values and get them back quickly. It loads into the runtime as an optional part, present whenever straightforward keyed storage is called for.

#### sim-table-http

It lets a trusted host treat direct HTTP resources as table entries under explicit network permission.

This backend points a table at a base HTTP address. A key becomes one resource under that address: reading performs a bounded request, writing sends a bounded update, and the response body passes through the selected SIM codec. The caller must hold network permission before any socket opens, so local programs can name remote resources without receiving network authority by accident.

#### sim-table-lazy

A lookup table whose values are worked out the first time you ask and then remembered.

This table holds names now but puts off producing their values until someone reads them. Each entry carries a small piece of work that runs at most once; the first read computes the value, and every read after that returns the saved result. That means a program can list many entries cheaply and pay only for the ones it actually opens, and never pay twice for the same one. It suits values that are expensive to build or drawn from somewhere slow. It loads into SIM as an optional part, present when a program wants keyed storage with deferred, remembered values.

#### sim-table-override

A stack of lookup tables where the top layers can cover entries in the ones beneath.

This backend lets you lay one or more tables over a base table and treat the pile as a single table. A lookup checks the layers from top to bottom and returns the first match, so an upper layer shadows whatever a lower one holds under the same name. That makes it easy to keep a shared base untouched while a thin layer on top adds or replaces a few entries just for one setting or one run. Removing the top layer brings the original values back. It loads into SIM as an optional part, present when a program wants layered, overridable storage.

### sim-stream

#### sim-lib-rank

A way to give every item in a well-defined space an exact number, so collections can be ordered and searched.

Rank turns a structured space of possibilities into a line of numbered positions. Given a grammar that describes what a valid item looks like -- a coordinate, a melody, a duration, a whole musical phrase -- it assigns each item a unique ordinal and can turn that ordinal back into the item exactly. This two-way mapping makes any conforming space indexable: you can order candidates, score them, and walk toward the best one by hill-climbing or beam search across neighbors. It ships bounded example spaces, including finite music spaces of pitches, rhythms, and progressions, plus codecs, ordering, and search over them. The mapping is deterministic, so the same space always numbers the same way.

#### sim-lib-stream-audio

The part that turns raw sound samples into observable streams and back again.

Sound in a computer is a long list of numbers, and this crate moves those numbers in and out of SIM's stream shape. It reads a PCM source into a stream of packets and writes a stream back out to a PCM sink, so recorded or generated audio can be watched and handled like any other moving data. Along the way it converts between common sample formats -- whole-number and floating-point -- and between interleaved and channel-separated layouts, checking that every conversion stays in range. The built-in source and sink work fully in memory and produce the same result every run, which makes audio behavior easy to test without a sound card.

#### sim-lib-stream-clock

The part that lines up a stream of data with real time or musical beats.

Streams arrive as a bare sequence of packets, and this crate answers the question of when each one happens. A clock chart maps positions in a stream to moments on a timeline: video frames counted per second, or MIDI ticks paced by a tempo map that can change speed partway through. You give it an instant and it returns the matching index; you give it an index and it returns the instant back, reporting whether the conversion was exact or rounded. All of this math stays in library space, so the runtime keeps carrying plain tick values while the richer clock meaning lives here, ready to align, seek, and compare streams by time or by beat.

#### sim-lib-stream-combinators

The building blocks for reshaping and combining streams of data as they flow.

Once data is moving as a stream, you rarely want it untouched. This crate supplies the stages that transform a stream lazily, only doing work as packets are pulled: reshape each item, drop the ones that do not match, group them into windows, or tap them to watch diagnostics go by. It can join two streams on a shared field, rank items by a numeric field, and project or redact parts of each record so sensitive fields never leak downstream. For live data it adds practical helpers -- resampling audio, a jitter buffer, a latency delay, and a rate gate for bursty events. A recording captures a finished stream so it can be replayed, seeked, and read again exactly.

#### sim-lib-stream-core

The shared shape for a run of changing data, so anything that moves can be watched packet by packet.

A stream in SIM is data that arrives over time -- audio samples, events, diagnostics, model output -- and this crate defines the common container for it. Every stream carries a small header describing what it is and which direction it flows, then delivers its contents as a sequence of packets. Each packet is a self-describing unit you can observe, count, buffer, and read back without guessing its layout. Buffers hold packets under a stated overflow policy, an inspector reports on what passed through, and a cassette captures a whole run so a finished stream can be stored and revisited. It is deliberately small: one honest value surface every other stream part builds on.

#### sim-lib-stream-device

A hardware-free device sample lane, so sensors can be modeled and tested before any real device is attached.

Device work often stalls on access to physical gear. This crate gives each device stream a small shared sample shape with a stable kind tag, a sequence number, and strict round-trip rules. A modeled source produces those samples from a counter, so a glasses, watch, badge, or lab rig can ship tests that never depend on a clock, network, driver, or sensor.

#### sim-lib-stream-prelude

The ready-made bundle that makes SIM's whole streaming toolkit available in one install.

This is the single package that gathers the streaming parts -- core packets, audio adapters, and combinators -- into one library the runtime can load at once. Installing it registers a set of named, permission-gated operations: open a deterministic in-memory MIDI or PCM source or sink, run a source-to-sink pipeline, apply combinator stages to reshape the flow, and browse any live stream as a card you can read. Each stream you open is tracked through a single handle that threads every operation, so opening, pumping, transforming, and inspecting all speak of the same thing. Because access is capability-gated, a host decides exactly which stream powers a given run may use.

#### sim-lib-topology

The part that turns a described network of connected steps into a checked, ready-to-run plan.

A topology is a wiring diagram: boxes that do something, joined by lines that say what feeds what. This crate lets you author that wiring as plain graph data, short text, a diagram, or a packaged file, then checks it and compiles it into a deterministic runtime plan. It confirms that nodes connect sensibly, carries along the capabilities a topology needs, and can hold small tests that state an input and the output expected from it. The compiled plan lists its nodes in a settled order, so the same description always produces the same shape. You can also present a topology as a readable card, making the structure something a person can browse rather than infer.

### sim-stream-host

#### sim-lib-stream-host

It plugs SIM's live streams into the real audio and MIDI gear on your machine and across your network.

This is the layer that connects SIM to the outside world of sound. When SIM needs to send or receive a stream of audio or musical notes, this part opens the connection to a real device, a software instrument, or a peer computer on your network, then keeps the packets flowing without stutters or dropped notes. It knows which devices and ports exist, picks the right place to run each piece of a stream, and reports honestly when a requested connection cannot be made instead of quietly doing something worse. A built-in stand-in device lets everything be tested and replayed without touching real hardware, so results stay repeatable.

### sim-web

#### sim-lib-intent

it turns a click, drag, or typed edit into a clear request the system can check before anything changes.

Every time you act on a value in the browser -- moving a node, setting a field, wiring two things together -- your gesture becomes a small, readable record of what you wanted. That record says who asked (a person or an agent), when, and against what. The system checks the request before it touches live state, so a bad edit is caught and explained instead of silently going through. The same record works whether the action came from your mouse or from an automated helper. Nothing is guessed from raw pixels; the intent is stated plainly and kept for review.

#### sim-lib-scene

it is the portable picture of what should appear on screen, saved as plain data you can inspect and share.

Before anything is drawn, the workspace builds a Scene: a tidy tree that describes the graph, table, plot, or panel to show. A Scene is ordinary SIM data, so it can be saved to a file, compared against yesterday's version, checked for correctness, sent across the network, or read by an agent. Only the browser turns a Scene into actual pixels; everything before that point just produces this description. Because the picture is data, you can snapshot it, test it, and diff two versions to see exactly what changed on screen -- all without a running browser in the loop.

#### sim-lib-view

it decides how any value should be shown and edited, and always has a sensible default ready.

A lens is a matched pair: a way to display a value and a way to edit it back. This crate chooses the right lens for whatever you open, using the same matching the runtime already uses elsewhere, so there is no second set of rules to learn. If nothing special fits, a universal default lens still shows the value cleanly, at a depth that suits you -- a light household view, a builder view, or a full systems view. You can stack lenses to look at one value several ways at once. Opening something unfamiliar never leaves you staring at a blank pane.

#### sim-lib-view-agent

it lets you wire up and watch a network of agents on a canvas, live, alongside the agents themselves.

This is the composer where you build a topology by hand: drop nodes, connect their ports, group them, move them around, and delete the pieces you do not need. The same canvas shows a run as it happens, so you can watch messages flow and replay what occurred. The striking part is that an automated agent can edit the very same graph you are looking at, at the same time, because you both act on one shared model. There is no separate copy that drifts out of step. What you draw is the actual system, and what runs is what you drew.

#### sim-lib-view-bridge

it lets people review and change BRIDGE packets in the same form agents use.

Open a BRIDGE packet and see its sender, move, profile, and parts in a surface-friendly review pane. A person can propose a patch, write a review, cast a scored vote, or record a receipt without leaving the packet model. The edit becomes the same collaboration record an agent reads, so there is one shared object instead of one browser copy and one model copy.

#### sim-lib-view-codec

it shows one value written several ways at once and lets you inspect how it matches a shape.

Open a single value and see it rendered side by side in several notations -- a Lisp-style form, JSON, a compact binary, an Algol-like form -- all at the same time. A probe panel checks that a value survives a round trip through each notation and back unchanged, so you can trust that what you read is faithful. A companion shape lens draws the matching tree, shows how parts bind, and, when a match fails, shows you a clear counterexample of what would not fit. The safe construction path is highlighted as the preferred way to rebuild a value, while broader evaluation stays behind a permission gate.

#### sim-lib-view-daw

it brings a full music studio -- timeline, mixer, effects, and synths -- into the browser workspace.

This lens family opens the SIM audio stack as a working studio. You arrange clips on a timeline, ride faders on mixer strips, watch live meters move, chain effect plugins in a rack, and shape sounds on synth panels with knobs and sliders. A modulation grid lets one control drive another, and you can read the signal as a waveform or a frequency spectrum. Every twist of a knob and every clip you move is committed as a checked edit against the real session, so the sound you hear reflects the actual saved arrangement. There is no separate audio model hiding behind the panels.

#### sim-lib-view-device

it turns open surface claims into a clear device envelope, so small screens and wearable edges degrade honestly.

Every surface can say what it can show, sense, emit, and refresh without becoming a hard-coded device family. This crate reads those claims into one shared envelope that ranks the surface by what is actually present. A watch, glasses display, phone relay, or desktop pane can all be compared through the same ladder, while still carrying their own open details.

#### sim-lib-view-doc

it is a writing surface where article structure, equations, figures, source text, and live results stay together.

This lens gives you a proper authoring workspace for technical writing, not a plain text box. A document is built from meaningful blocks -- sections, prose, equations, figures, tables, citations, and blocks that run live inside the page. You navigate by an outline and arrange blocks on a canvas. You can look at the same article two ways at once: the clean formatted reading view and the underlying source, side by side, each a lens on the one document. Because the document is one stored markup value, an embedded live block shows a real computed result right where it belongs in your argument.

#### sim-lib-view-math

it turns numbers, matrices, and formulas into plots and grids you can see and adjust.

This lens family makes math visual and hands-on. Numeric series and functions become plots you can read at a glance. Matrices and tensors open as editable grids, so you can change a slice and see the effect. A symbolic formula shows as a tree you can explore. Sliders and knobs let you sweep a parameter and watch the result move, then snapshot a setting and compare it against another. Throughout, the display reads numbers from SIM's own number kinds, while the runtime value stays the single source of truth -- so what you tweak on screen is the same number the system actually holds.

#### sim-lib-view-wasm-frame

it is the local helper that renders a value to a screen picture, folds your gestures into edits, and commits them in place.

This crate is the plain glue that a browser shell leans on to do the everyday view loop against a value held right here in the process. It renders a value into the shared scene picture, gathers raw gestures and folds them into clear edit requests, applies an accepted edit to the value, and reports back the small difference so the screen can update just the part that changed. It shares the same view, edit, and scene rules the rest of the workspace uses, so its behavior lines up with the browser adapters without carrying any separate display logic of its own.

#### sim-lib-web-bridge

it is the pipe that carries your edits out and the fresh pictures back, no matter where the runtime actually runs.

The bridge connects the browser workspace to a running system without you caring where that system lives. It can talk to a runtime inside the same browser tab, a server on your own machine, or a server across the network, and it uses one common way of asking rather than a different setup for each. For tests, it can replay a recorded session so results come out the same every time. Both a person at the browser and an automated agent are equal peers on this one channel, so edits and updated screens flow through the same place for everyone.

#### sim-lib-web-layout

it holds the whole arrangement of your workspace -- panes, tabs, and docks -- as data you can save and restore.

Your entire workspace layout is kept as one piece of SIM data: the panes, tabs, splits, docks, floating inspectors, overlays, which resources are open, which lens each one uses, the current mode, and the session it belongs to. Because that arrangement is plain data, you can save it, share it with someone else, keep versions of it, compare two of them, and bring it back exactly as it was. Restoring a session is simply reading the value back in. Rearranging your panes is editing that value, so the shape of your desk is something you own and can move around freely.

#### sim-web-shell

it is the program you run to open the SIM workspace in a browser.

This is the server that serves the SIM browser workspace. It bundles the browser assets it needs and exposes the shared cookbook services, so starting it gives you a running front door to the whole view stack. In the browser, the shell stays deliberately thin: it paints the scene pictures it receives and sends your gestures back as edit requests, nothing more. It also offers a cache view over the generated site graph, the constellation index, the retrieval radar, and the guideline firewall reports, so you can browse those alongside your work. It carries no second data model and no second set of rules.
