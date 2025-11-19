<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Internal Noterist (Failsafe)</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f4f7f9; margin: 0; padding: 0; display: flex; justify-content: center; min-height: 100vh; align-items: flex-start; }
        .container { background-color: #ffffff; border-radius: 12px; box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); padding: 20px; width: 90%; max-width: 700px; font-size: 14px; display: flex; flex-direction: column; position: relative; margin-bottom: 60px; }
        #pageTitle { text-align: center; font-size: 24px; font-weight: 600; color: #333; margin-bottom: 5px; position: relative; }
        #timerDisplay { position: absolute; bottom: -20px; left: 50%; transform: translateX(-50%); font-size: 12px; color: #777; }
        
        /* Status Toast */
        #statusIndicator { position: fixed; bottom: 10px; right: 10px; padding: 8px 12px; border-radius: 4px; font-size: 12px; font-weight: bold; color: white; opacity: 0.9; pointer-events: none; z-index: 1000; transition: all 0.3s ease; background-color: #6c757d; }
        .status-saved { background-color: #28a745 !important; }
        .status-error { background-color: #dc3545 !important; }
        .status-active { background-color: #007bff !important; }

        label { display: block; margin-bottom: 6px; font-weight: 500; color: #555; }
        input, textarea, select { width: calc(100% - 16px); padding: 8px; margin-bottom: 12px; border: 1px solid #ddd; border-radius: 6px; box-sizing: border-box; font-size: 14px; transition: border-color 0.3s ease; }
        input:focus, textarea:focus, select:focus { border-color: #007bff; outline: none; }
        button { padding: 10px 20px; background-color: #007bff; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 14px; transition: background-color 0.3s ease; margin-right: 8px; }
        button:hover { background-color: #0056b3; }
        
        /* Logic Styles */
        .disabled { color: #ccc !important; pointer-events: none; }
        .crossed-out { text-decoration: line-through; color: #ccc !important; pointer-events: none; opacity: 0.6; }
        
        #output { margin-top: 10px; padding: 15px; border: 1px solid #eee; border-radius: 6px; background-color: #f9f9f9; white-space: pre-wrap; font-size: 14px; line-height: 1.4; cursor: pointer; }
        #outputButtons { margin-top: 15px; display: none; }
        #error-message { color: #d9534f; margin-top: 8px; font-weight: bold; animation: blinker 1s linear infinite; }
        @keyframes blinker { 50% { opacity: 0; } }
        #undoCR { margin-left: 8px; display: none; } 
        #screenshots { height: 160px; }
        .form-row { display: flex; gap: 15px; }
        .form-row > div { flex: 1; }
        .alert-box { display: none; color: red; font-weight: bold; margin-top: 15px; margin-bottom: 10px; padding: 10px; border: 1px solid red; border-radius: 6px; background-color: #ffebee; text-align: center; }

        /* Multiselect & Dropdowns */
        .multiselect-container { position: relative; margin-bottom: 12px; }
        .multiselect-button { width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 6px; background-color: #fff; text-align: left; cursor: pointer; font-size: 14px; color: #333; box-sizing: border-box; position: relative; }
        .multiselect-button::after { content: '▼'; position: absolute; right: 10px; top: 50%; transform: translateY(-50%); font-size: 10px; color: #777; }
        .multiselect-options { display: none; position: absolute; top: 100%; left: 0; width: 100%; border: 1px solid #ddd; border-radius: 0 0 6px 6px; background-color: #fff; max-height: 220px; overflow-y: auto; z-index: 1000; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        .multiselect-options.active { display: block; }
        .multiselect-options label { display: block; padding: 8px 12px; cursor: pointer; font-weight: normal; }
        .multiselect-options label:hover { background-color: #f4f7f9; }
        .multiselect-options input[type="checkbox"] { margin-right: 8px; width: auto; }
        .inline-group label { display: inline-block; margin-right: 15px; font-weight: normal; }
        .inline-group input { width: auto; margin-bottom: 0; vertical-align: middle; }
        
        #storageWarning { display:none; background: #ffdddd; color: #d8000c; padding: 10px; text-align: center; margin-bottom: 10px; border-radius: 6px; }
    </style>
</head>
<body>
    <div class="main-content">
        <div class="container">
            <div id="storageWarning">⚠️ WARNING: Local Storage is disabled in your browser. Your data will NOT execute save.</div>
            <div id="pageTitle">Rion's Notes and Tracker<div id="timerDisplay"></div></div>
            
            <form id="inputForm" autocomplete="off">
                <label>Status Tracker:</label>
                <div id="statusTrackerContainer" class="inline-group" style="margin-bottom: 15px;">
                    <label id="labelNormalReview"><input type="checkbox" id="statusNormalReview" value="Normal Review"> Normal Review</label>
                    <label id="labelEscalatedDelay"><input type="checkbox" id="statusEscalatedDelay" value="Escalated Delay Response"> Escalated Delay Response</label>
                    <label id="labelEscalatedL2L3"><input type="checkbox" id="statusEscalatedL2L3" value="Escalated L2/L3"> Escalated L2/L3</label>
                    
                    <label id="labelSentCR"><input type="checkbox" id="statusSentCR" value="Sent CR"> Sent CR</label>
                    <label id="labelInternalNotes"><input type="checkbox" id="statusInternalNotes" value="Internal notes"> Internal notes</label>
                    <label id="labelSolved"><input type="checkbox" id="statusSolved" value="Marked as Solved"> Marked as Solved</label>
                    <label id="labelTracked"><input type="checkbox" id="statusTracked" value="Tracked"> Tracked</label>
                </div>
                
                <div class="form-row">
                    <div>
                        <label for="verificationStage">Verification Stage :</label>
                        <select id="verificationStage" name="verificationStage">
                            <option value="">Select Verification Stage</option>
                            <option value="Pre-moderation">Pre-moderation</option>
                            <option value="Screening">Screening</option>
                            <option value="Pre-Verification">Pre-Verification</option>
                            <option value="Brand Verification">Brand Verification</option>
                            <option value="Verification">Verification</option>
                            <option value="Extended Enforcement">Extended Enforcement</option>
                            <option value="Approval">Approval</option>
                            <option value="Post Approval">Post Approval</option>
                        </select>
                    </div>
                    <div>
                        <label for="reviewStatus">Review Status :</label>
                        <select id="reviewStatus" name="reviewStatus">
                            <option value="">Select Review Status</option>
                            <option value="Failed Review">Failed Review</option>
                            <option value="Escalated">Escalated</option>
                            <option value="Escalated (L3 CR)">Escalated (L3 CR)</option>
                            <option value="Escalated (Resolved)">Escalated (Resolved)</option>
                            <option value="Escalated (LGTM / Custom CR)">Escalated (LGTM / Custom CR)</option>
                            <option value="Escalated (LGTM / CR Combination)">Escalated (LGTM / CR Combination)</option>
                            <option value="Acknowledgement">Acknowledgement</option>
                            <option value="Approved">Approved</option>
                        </select>
                    </div>
                </div>

                <label for="issue">Issue :</label>
                <textarea id="issue" name="issue"></textarea>

                <label>App Type:</label>
                <div class="multiselect-container" id="appTypeContainer">
                    <div class="multiselect-button" id="appTypeButton">Select App Type(s)</div>
                    <div class="multiselect-options" id="appTypeOptions">
                        <label><input type="checkbox" value="Web"> Web</label>
                        <label><input type="checkbox" value="Android"> Android</label>
                        <label><input type="checkbox" value="IOS"> IOS</label>
                        <label><input type="checkbox" value="Native Desktop"> Native Desktop</label>
                        <label><input type="checkbox" value="Chrome Extension"> Chrome Extension</label>
                        <label><input type="checkbox" value="Google Workspace Add-ons"> Google Workspace Add-ons</label>
                        <label><input type="checkbox" value="N/A"> N/A</label>
                    </div>
                </div>

                <label>Tool Used:</label>
                <div class="multiselect-container" id="toolUsedContainer">
                    <div class="multiselect-button" id="toolUsedButton">Select Tool(s) Used</div>
                    <div class="multiselect-options" id="toolUsedOptions">
                        <label><input type="checkbox" value="N/A"> N/A</label>
                        <label><input type="checkbox" value="Browser"> Browser</label>
                        <label><input type="checkbox" value="Demo Video"> Demo Video</label>
                        <label><input type="checkbox" value="Mobile Harness"> Mobile Harness</label>
                        <label><input type="checkbox" value="Pixel"> Pixel</label>
                    </div>
                </div>

                <label for="scopes">Scopes :</label>
                <textarea id="scopes" name="scopes">N/A</textarea>
                
                <label for="possibleCRs">Possible CRs:</label>
                <textarea id="possibleCRs" name="possibleCRs">N/A</textarea>
                
                <div class="multiselect-container" id="crContainer">
                    <div class="multiselect-button" id="crButton">Add Possible CR(s)...</div>
                    <div class="multiselect-options" id="crOptions">
                        <input type="text" id="crSearch" class="multiselect-search" placeholder="Search for a CR..." style="width:100%; box-sizing:border-box;">
                        <div id="crCheckboxContainer"></div>
                    </div>
                </div>
                <button type="button" id="undoCR" onclick="app.undoLastCR()">Undo Last</button>

                <label for="escalationID">Escalation ID :</label>
                <input type="text" id="escalationID" name="escalationID" value="N/A">
                <label for="lgtm">LGTM:</label>
                <input type="text" id="lgtm" name="lgtm" value="N/A">

                <label for="screenshots">Screenshots (URLs):</label>
                <textarea id="screenshots" name="screenshots"></textarea>

                <div style="margin-top:15px;">
                    <button type="button" id="displayButton" onclick="app.displayInput()">Display Input</button>
                    <button type="button" onclick="app.resetInputs()">Clear</button>
                    <!-- Manual Restore Button in case of emergency -->
                    <button type="button" onclick="app.loadData(true)" style="background-color:#6c757d; float:right;">Force Restore Data</button>
                </div>
                
                <div id="error-message"></div>
            </form>
            
            <div id="ada-alert" class="alert-box"></div>
            <div id="homepage-alert" class="alert-box"></div>
            
            <div id="output"></div>
            <div id="outputButtons">
                <button type="button" onclick="app.selectAllOutput()">Select All</button>
                <button type="button" onclick="app.clearOutput()">Clear Output</button>
            </div>
        </div>
    </div>
    
    <div id="statusIndicator">Initializing...</div>

    <script>
        const app = {
            storageKey: 'rion_notes_failsafe_v5', // Unique key for this version
            timerStarted: false,
            timerInterval: null,
            startTimeTimestamp: 0,
            defaultScreenshots: `PV Pre-auto:\nPV Post-auto:\nGA:\n\nHP:\nPP:\nDrafted/Sent CR:`,
            saveTimeout: null,
            // CRITICAL: This flag prevents saving until we are 100% sure loading finished
            isSafeToSave: false, 

            showStatus: function(msg, type) {
                const el = document.getElementById('statusIndicator');
                el.textContent = msg;
                el.className = '';
                if(type === 'saved') el.classList.add('status-saved');
                else if(type === 'error') el.classList.add('status-error');
                else el.classList.add('status-active');
            },

            // --- 1. CHECK STORAGE ---
            checkStorage: function() {
                try {
                    localStorage.setItem('test', 'test');
                    localStorage.removeItem('test');
                    return true;
                } catch(e) {
                    document.getElementById('storageWarning').style.display = 'block';
                    this.showStatus("Storage Disabled", "error");
                    return false;
                }
            },

            // --- 2. LOGIC CORE (Chain & Rules) ---
            updateStatusLogic: function() {
                const els = {
                    normal: document.getElementById('statusNormalReview'),
                    delay: document.getElementById('statusEscalatedDelay'),
                    l2l3: document.getElementById('statusEscalatedL2L3'),
                    sent: document.getElementById('statusSentCR'),
                    notes: document.getElementById('statusInternalNotes'),
                    solved: document.getElementById('statusSolved'),
                    tracked: document.getElementById('statusTracked')
                };

                const enable = (el) => { 
                    el.disabled = false; 
                    const lbl = document.getElementById(el.id.replace('status', 'label'));
                    if(lbl) lbl.classList.remove('crossed-out', 'disabled');
                };
                const disable = (el) => { 
                    el.disabled = true; 
                    const lbl = document.getElementById(el.id.replace('status', 'label'));
                    if(lbl) lbl.classList.add('crossed-out', 'disabled');
                };

                // Reset to enabled
                Object.values(els).forEach(enable);

                // 1. Mutual Exclusivity
                if (els.normal.checked) { disable(els.delay); disable(els.l2l3); }
                else if (els.delay.checked) { disable(els.normal); disable(els.l2l3); }
                else if (els.l2l3.checked) { disable(els.normal); disable(els.delay); }

                // 2. Conflict Rules
                const statusVal = document.getElementById("reviewStatus").value;
                if (els.normal.checked && statusVal === "Escalated") { disable(els.sent); disable(els.solved); }
                else if (els.delay.checked) { disable(els.solved); }
                else if (els.l2l3.checked) { disable(els.sent); disable(els.notes); disable(els.solved); }

                // 3. STRICT SEQUENTIAL CHAIN
                const chain = [{el: els.sent}, {el: els.notes}, {el: els.solved}, {el: els.tracked}];
                const primaryActive = els.normal.checked || els.delay.checked || els.l2l3.checked;
                
                let allowed = primaryActive;

                chain.forEach((item) => {
                    if (item.el.disabled) return; // If disabled by rules, skip processing
                    
                    if (!allowed) {
                        disable(item.el);
                    } else {
                        enable(item.el);
                        // For the next item to be allowed, THIS item must be checked
                        allowed = item.el.checked;
                    }
                });
            },

            // --- 3. STORAGE ---
            saveData: function() {
                // THE GATEKEEPER: If this is false, we simply do not save.
                if (!this.isSafeToSave) return;

                if (this.saveTimeout) clearTimeout(this.saveTimeout);
                this.saveTimeout = setTimeout(() => {
                    try {
                        const data = {};
                        // Inputs
                        ["verificationStage", "reviewStatus", "issue", "scopes", "possibleCRs", "escalationID", "lgtm", "screenshots"].forEach(id => {
                            const el = document.getElementById(id);
                            if(el) data[id] = el.value;
                        });
                        // Checkboxes
                        document.querySelectorAll('#statusTrackerContainer input').forEach(el => data[el.id] = el.checked);
                        // Multiselects
                        data.appTypeOptions = this.harvestMultiselect('appTypeOptions');
                        data.toolUsedOptions = this.harvestMultiselect('toolUsedOptions');
                        // Timer
                        data.timerStartTimestamp = this.timerStarted ? this.startTimeTimestamp : null;

                        localStorage.setItem(this.storageKey, JSON.stringify(data));
                        this.showStatus("Saved", "saved");
                    } catch(e) { 
                        console.error(e);
                        this.showStatus("Save Failed", "error");
                    }
                }, 500);
            },

            loadData: function(force = false) {
                this.showStatus("Loading...", "active");
                try {
                    const json = localStorage.getItem(this.storageKey);
                    if (!json) {
                        document.getElementById('screenshots').value = this.defaultScreenshots;
                        if(!force) this.isSafeToSave = true; // Safe to save if nothing to load
                        this.showStatus("Ready (New)", "active");
                        return;
                    }
                    const data = JSON.parse(json);
                    
                    // Inputs
                    ["verificationStage", "reviewStatus", "issue", "scopes", "possibleCRs", "escalationID", "lgtm", "screenshots"].forEach(id => {
                        const el = document.getElementById(id);
                        if(el && data[id] !== undefined) el.value = data[id];
                    });
                    // Checkboxes
                    document.querySelectorAll('#statusTrackerContainer input').forEach(el => {
                        if(data[el.id] !== undefined) el.checked = data[el.id];
                    });
                    // Multiselects
                    this.restoreMultiselect('appTypeOptions', 'appTypeButton', data.appTypeOptions);
                    this.restoreMultiselect('toolUsedOptions', 'toolUsedButton', data.toolUsedOptions);
                    // Timer
                    if(data.timerStartTimestamp) this.resumeTimer(data.timerStartTimestamp);

                    if(force) alert("Data Force Restored");
                    this.showStatus("Data Restored", "active");
                } catch(e) { 
                    console.error(e); 
                    this.showStatus("Load Error", "error");
                } finally {
                    this.updateStatusLogic();
                    this.updateCRDropdown();
                }
            },

            // --- 4. DOM UTILS ---
            harvestMultiselect: function(id) {
                return [...document.querySelectorAll(`#${id} input`)].map(c => ({ value: c.value, checked: c.checked }));
            },
            restoreMultiselect: function(contId, btnId, items) {
                if(!items) return;
                const chks = document.querySelectorAll(`#${contId} input`);
                items.forEach(i => {
                    const cb = [...chks].find(c => c.value === i.value);
                    if(cb) cb.checked = i.checked;
                });
                this.updateMultiselectText(document.getElementById(btnId), chks);
            },
            updateMultiselectText: function(btn, chks) {
                const sel = [...chks].filter(c => c.checked).map(c => c.value);
                btn.textContent = sel.length > 0 ? sel.join(', ') : (btn.id.includes('app') ? 'Select App Type(s)' : 'Select Tool(s) Used');
            },
            setupMultiselect: function(btnId, contId) {
                const btn = document.getElementById(btnId);
                const opt = document.getElementById(contId);
                const chks = opt.querySelectorAll('input');
                btn.addEventListener('click', (e) => { e.stopPropagation(); opt.classList.toggle('active'); });
                chks.forEach(c => c.addEventListener('change', () => {
                    this.updateMultiselectText(btn, chks);
                    this.startTimer(); this.saveData();
                }));
            },

            // --- 5. TIMER ---
            startTimer: function() {
                if(!this.timerStarted) { this.resumeTimer(Date.now()); this.saveData(); }
            },
            resumeTimer: function(ts) {
                this.startTimeTimestamp = ts;
                this.timerStarted = true;
                if(this.timerInterval) clearInterval(this.timerInterval);
                this.timerInterval = setInterval(() => {
                    const diff = Math.floor((Date.now() - this.startTimeTimestamp) / 1000);
                    const m = Math.floor(diff/60).toString().padStart(2,'0');
                    const s = (diff%60).toString().padStart(2,'0');
                    document.getElementById("timerDisplay").textContent = `Time: ${m}:${s}`;
                }, 1000);
            },
            stopTimer: function() {
                clearInterval(this.timerInterval);
                this.timerStarted = false;
                document.getElementById("timerDisplay").textContent = "";
            },

            // --- 6. CR LOGIC ---
            crOptions: { Screening: [ "first_party_application", "project_deletion", "abuse_terms_of_service", "safe_Browse_check" ], "Pre-Verification": [ "homepage_unresponsive", "homepage_unverified", "homepage_redirection", "homepage_shortened", "homepage_privacy_policy_missing", "privacy_policy_responsiveness", "privacy_policy_formatting", "privacy_policy_branding", "privacy_policy_unique_url", "privacy_policy_page_content", "app_scope_not_justified", "app_farm", "test_account_unclear_login", "test_account_unauthorized", "test_account_constraint", "video_link_inaccessible", "video_application_mismatch", "video_oauth_missing", "app_demo_missing" ], "Brand Verification": [ "homepage_login", "homepage_purpose_missing", "brand_app_name_mismatch", "brand_logo_impersonation", "brand_app_name_impersonation" ], Verification: [ "privacy_data_collection", "privacy_data_use", "privacy_data_sharing", "privacy_data_protection", "privacy_data_retention", "privacy_data_sale", "privacy_prohibited_use", "privacy_prohibited_transfer", "app_inappropriate_use_case", "min_scope_future_capability", "min_scope_use_case_mismatch", "min_scope_consent_mismatch", "min_scope_violation" ], "Extended Enforcement": [ "CASA_Verify", "CASA Tier 3 CR" ], Approval: [ "Brand Approval CR", "Sensitive Approval CR", "Final Approval CR" ], "Post Approval": [ "48cb2327", "Post Approval CR 2", "Post Approval CR 3" ] },
            crExclusionRules: { "homepage_unresponsive": ["homepage_unverified", "homepage_redirection", "homepage_privacy_policy_missing", "privacy_policy_unique_url", "privacy_policy_page_content"], "privacy_policy_responsiveness": ["privacy_policy_formatting", "privacy_policy_branding", "privacy_policy_unique_url", "privacy_policy_page_content"], "test_account_unclear_login": ["video_link_inaccessible", "video_application_mismatch", "video_oauth_missing", "app_demo_missing"], "test_account_unauthorized": ["video_link_inaccessible", "video_application_mismatch", "video_oauth_missing", "app_demo_missing"], "test_account_constraint": ["video_link_inaccessible", "video_application_mismatch", "video_oauth_missing", "app_demo_missing"], "video_link_inaccessible": ["test_account_unclear_login", "test_account_unauthorized", "test_account_constraint"], "video_application_mismatch": ["test_account_unclear_login", "test_account_unauthorized", "test_account_constraint"], "video_oauth_missing": ["test_account_unclear_login", "test_account_unauthorized", "test_account_constraint"], "app_demo_missing": ["test_account_unclear_login", "test_account_unauthorized", "test_account_constraint"] },

            updateCRDropdown: function() {
                const stg = document.getElementById("verificationStage").value;
                const sts = document.getElementById("reviewStatus").value;
                const cont = document.getElementById('crCheckboxContainer');
                cont.innerHTML = '';
                let opts = [];
                if (sts === "Acknowledgement") opts = Object.entries({ "NEW_SUBMISSION_ACK": "ACK CR", "bb5b460b": "Vauge Response", "825207b9": "Personal Use", "57e2890d": "Internal Use", "e565463f": "Development / Testing Apps", "fa9f227": "GMail SMTP Plug In" }).map(([v, t]) => ({ value: v, text: t }));
                else if (this.crOptions[stg]) opts = this.crOptions[stg].map(v => ({ value: v, text: v }));
                
                const curs = document.getElementById("possibleCRs").value.split(",").map(s => s.trim()).filter(s => s && s !== "N/A");

                opts.forEach(o => {
                    const lbl = document.createElement('label');
                    const chk = document.createElement('input');
                    chk.type = 'checkbox'; chk.value = o.value;
                    if (curs.includes(o.value)) chk.checked = true;
                    
                    let isExc = false;
                    curs.forEach(s => { if(s!==o.value) { if((this.crExclusionRules[s]||[]).includes(o.value)) isExc=true; Object.keys(this.crExclusionRules).forEach(k=>{if(this.crExclusionRules[k].includes(o.value)&&s===k)isExc=true;}); } });
                    if (isExc) { chk.disabled=true; lbl.classList.add('disabled'); }
                    
                    chk.addEventListener('change', (e) => {
                        let l = document.getElementById("possibleCRs").value.split(",").map(s=>s.trim()).filter(s=>s&&s!=="N/A");
                        if(e.target.checked) { if(!l.includes(o.value)) l.push(o.value); } else { l = l.filter(x=>x!==o.value); }
                        document.getElementById("possibleCRs").value = l.length ? l.join(", ") : "N/A";
                        this.updateCRDropdown(); this.startTimer(); this.saveData();
                    });
                    lbl.appendChild(chk); lbl.appendChild(document.createTextNode(` ${o.text}`)); cont.appendChild(lbl);
                });
                document.getElementById("undoCR").style.display = curs.length ? "inline-block" : "none";
            },

            undoLastCR: function() {
                let l = document.getElementById("possibleCRs").value.split(",").map(s=>s.trim()).filter(s=>s&&s!=="N/A");
                if(l.length) { l.pop(); document.getElementById("possibleCRs").value = l.length ? l.join(", ") : "N/A"; this.updateCRDropdown(); this.saveData(); }
            },

            displayInput: function() {
                const stg = document.getElementById("verificationStage").value;
                const sts = document.getElementById("reviewStatus").value;
                const err = document.getElementById("error-message");
                err.innerHTML=""; document.getElementById("ada-alert").style.display="none"; document.getElementById("homepage-alert").style.display="none"; document.getElementById("output").innerHTML=""; document.getElementById("outputButtons").style.display="none";

                if(!stg && sts!=="Acknowledgement") { err.innerHTML="<b>Select Verification Stage</b>"; return; }
                if(!sts) { err.innerHTML="<b>Select Review Status</b>"; return; }
                
                const apps = this.harvestMultiselect('appTypeOptions').filter(x=>x.checked).map(x=>x.value);
                if(!apps.length) { err.innerHTML="<b>Select App Type</b>"; return; }

                const tools = this.harvestMultiselect('toolUsedOptions').filter(x=>x.checked).map(x=>x.value);
                const crs = document.getElementById("possibleCRs").value;
                const eid = document.getElementById("escalationID").value;
                
                if(sts!=="Escalated" && (crs==="N/A"||!crs)) { err.innerHTML="<b>Input CRs</b>"; return; }
                if(sts==="Escalated" && (eid==="N/A"||!eid)) { err.innerHTML="<b>Input Escalation ID</b>"; return; }

                if(stg==="Extended Enforcement") { document.getElementById("ada-alert").innerHTML="<b>CHECK ADA PORTAL</b>"; document.getElementById("ada-alert").style.display="block"; }
                if(stg==="Pre-Verification"&&crs.includes("homepage_unverified")) { document.getElementById("homepage-alert").innerHTML="<b>CHECK EMAILS</b>"; document.getElementById("homepage-alert").style.display="block"; }
                
                const iss = document.getElementById("issue").value || "N/A";
                const scp = (document.getElementById("scopes").value.match(/\d+/g)||[]).join(", ")||"N/A";
                const lgtm = document.getElementById("lgtm").value;
                const shots = document.getElementById("screenshots").value;
                
                let out = `<b>Verification Stage :</b> ${stg}<br><b>Issue :</b> ${iss}<br><b>Review Status :</b> ${sts}<br><b>App Type:</b> ${apps.join(', ')}<br><b>Tool Used :</b> ${tools.join(', ')||"N/A"}<br><b>Scopes :</b> ${scp}<br><b>Possible CRs :</b> ${crs}<br><b>Escalation ID :</b> ${eid}`;
                if(lgtm!=="N/A") out+=`<br><b>LGTM :</b> ${lgtm}`;
                if(shots&&shots!==this.defaultScreenshots) out+=`<br><br><b>Screenshots :</b><br>${shots}`;
                
                document.getElementById("output").innerHTML=out;
                document.getElementById("outputButtons").style.display="block";
                this.startTimer();
            },

            resetInputs: function() {
                if(!document.getElementById('statusTracked').checked) { document.getElementById("error-message").innerHTML="<b>Mark 'Tracked' before clearing.</b>"; return; }
                document.getElementById('inputForm').reset();
                document.getElementById("possibleCRs").value="N/A"; document.getElementById("scopes").value="N/A"; document.getElementById("escalationID").value="N/A"; document.getElementById("lgtm").value="N/A";
                document.getElementById("screenshots").value=this.defaultScreenshots;
                document.querySelectorAll('#statusTrackerContainer input').forEach(el=>el.checked=false);
                this.updateStatusLogic(); this.updateCRDropdown();
                this.updateMultiselectText(document.getElementById('appTypeButton'), document.querySelectorAll('#appTypeOptions input'));
                this.updateMultiselectText(document.getElementById('toolUsedButton'), document.querySelectorAll('#toolUsedOptions input'));
                this.stopTimer();
                document.getElementById("output").innerHTML=""; document.getElementById("outputButtons").style.display="none"; document.getElementById("ada-alert").style.display="none"; document.getElementById("homepage-alert").style.display="none";
                
                // FORCE CLEAR STORAGE (Unlock for this action only)
                localStorage.removeItem(this.storageKey);
                this.showStatus("Cleared", "cleared");
            },

            selectAllOutput: function() { const r=document.createRange(); r.selectNodeContents(document.getElementById("output")); window.getSelection().removeAllRanges(); window.getSelection().addRange(r); },
            clearOutput: function() { document.getElementById("output").innerHTML=""; document.getElementById("outputButtons").style.display="none"; },

            init: function() {
                if(!this.checkStorage()) return;

                this.setupMultiselect('appTypeButton', 'appTypeOptions');
                this.setupMultiselect('toolUsedButton', 'toolUsedOptions');
                
                const crBtn = document.getElementById('crButton'); const crOpt = document.getElementById('crOptions'); const crSearch = document.getElementById('crSearch');
                crBtn.addEventListener('click', (e) => { e.stopPropagation(); if(document.getElementById("verificationStage").value||document.getElementById("reviewStatus").value==="Acknowledgement") { crOpt.classList.toggle('active'); if(crOpt.classList.contains('active')) crSearch.focus(); } else alert("Select Verification Stage first."); });
                crSearch.addEventListener('keyup', (e) => { const f=e.target.value.toLowerCase(); document.querySelectorAll('#crCheckboxContainer label').forEach(l=>l.style.display=l.textContent.toLowerCase().includes(f)?"":"none"); });
                window.addEventListener('click', (e) => { document.querySelectorAll('.multiselect-options').forEach(o=>{ if(!o.parentElement.contains(e.target)) o.classList.remove('active'); }); });

                // 1. LOAD DATA
                this.loadData();

                // 2. DELAYED STARTUP - The Silver Bullet
                // We wait 1 second after loading before we even attach the save listeners.
                // This makes it impossible for the empty form to overwrite data during load.
                setTimeout(() => {
                    // Enable Saving
                    this.isSafeToSave = true;
                    this.showStatus("Ready", "active");

                    // Attach Listeners *NOW*
                    const inputs = ["verificationStage", "reviewStatus", "issue", "scopes", "possibleCRs", "escalationID", "lgtm", "screenshots"];
                    inputs.forEach(id => { const el=document.getElementById(id); if(el) { el.addEventListener('input', ()=>{this.startTimer();this.saveData();}); el.addEventListener('change', ()=>{this.startTimer();this.saveData();}); } });
                    
                    document.querySelectorAll('#statusTrackerContainer input').forEach(el => el.addEventListener('change', ()=>{ this.startTimer(); this.updateStatusLogic(); this.saveData(); }));
                    document.getElementById("reviewStatus").addEventListener('change', ()=>{ this.updateStatusLogic(); this.saveData(); });
                    document.getElementById("verificationStage").addEventListener("change", ()=>{ if(document.getElementById("verificationStage").value==="Approval") document.getElementById("reviewStatus").value="Approved"; this.updateCRDropdown(); this.saveData(); });
                    document.getElementById("possibleCRs").addEventListener("input", ()=>{ this.updateCRDropdown(); this.saveData(); });
                }, 1000); // 1 Second Delay
            }
        };

        document.addEventListener('DOMContentLoaded', () => app.init());
    </script>
</body>
</html>
