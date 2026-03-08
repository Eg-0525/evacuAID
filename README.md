import { useState } from "react";

const COLORS = {
  navy: "#0D2137",
  navyLight: "#1A3A5C",
  red: "#C0392B",
  redLight: "#E74C3C",
  sky: "#2E86AB",
  skyLight: "#5BA4C8",
  cream: "#F5F0E8",
  creamDark: "#EDE8DF",
  gold: "#E8A838",
  white: "#FEFEFE",
  textDark: "#1A1A2E",
  textMid: "#4A5568",
};

const styles = {
  shell: {
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
    minHeight: "100vh",
    background: "linear-gradient(135deg, #0D2137 0%, #1A3A5C 50%, #0D2137 100%)",
    fontFamily: "'Georgia', serif",
    padding: "20px",
  },
  phone: {
    width: "375px",
    height: "720px",
    background: COLORS.cream,
    borderRadius: "40px",
    overflow: "hidden",
    display: "flex",
    flexDirection: "column",
    boxShadow: "0 30px 80px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.2)",
    position: "relative",
    border: "1px solid rgba(255,255,255,0.1)",
  },
  header: {
    background: `linear-gradient(135deg, ${COLORS.navy} 0%, ${COLORS.navyLight} 100%)`,
    padding: "20px 20px 16px",
    display: "flex",
    alignItems: "center",
    justifyContent: "space-between",
    flexShrink: 0,
  },
  headerTitle: {
    color: COLORS.white,
    fontSize: "22px",
    fontWeight: "700",
    letterSpacing: "1px",
    margin: 0,
  },
  headerSub: {
    color: COLORS.gold,
    fontSize: "10px",
    letterSpacing: "2px",
    textTransform: "uppercase",
    marginTop: "2px",
  },
  alertBanner: {
    background: `linear-gradient(90deg, ${COLORS.red} 0%, ${COLORS.redLight} 100%)`,
    color: "white",
    textAlign: "center",
    padding: "8px 16px",
    fontSize: "12px",
    letterSpacing: "0.5px",
    fontWeight: "600",
    flexShrink: 0,
  },
  content: {
    flex: 1,
    overflowY: "auto",
    padding: "20px",
    background: COLORS.cream,
  },
  pageTitle: {
    fontSize: "24px",
    fontWeight: "700",
    color: COLORS.navy,
    margin: "0 0 4px 0",
  },
  pageSubtitle: {
    fontSize: "13px",
    color: COLORS.textMid,
    margin: "0 0 20px 0",
    fontStyle: "italic",
  },
  card: {
    background: COLORS.white,
    borderRadius: "16px",
    padding: "18px",
    marginBottom: "14px",
    boxShadow: "0 4px 16px rgba(13,33,55,0.08)",
    border: `1px solid rgba(13,33,55,0.06)`,
  },
  label: {
    fontSize: "11px",
    fontWeight: "700",
    letterSpacing: "1.5px",
    textTransform: "uppercase",
    color: COLORS.sky,
    display: "block",
    marginBottom: "6px",
    marginTop: "12px",
  },
  input: {
    width: "100%",
    padding: "11px 14px",
    borderRadius: "10px",
    border: `1.5px solid ${COLORS.creamDark}`,
    fontFamily: "Georgia, serif",
    fontSize: "14px",
    color: COLORS.textDark,
    background: COLORS.cream,
    outline: "none",
    boxSizing: "border-box",
    transition: "border-color 0.2s",
  },
  btnPrimary: {
    width: "100%",
    padding: "15px",
    marginTop: "14px",
    border: "none",
    borderRadius: "14px",
    background: `linear-gradient(135deg, ${COLORS.navy} 0%, ${COLORS.navyLight} 100%)`,
    color: "white",
    fontSize: "15px",
    fontWeight: "700",
    letterSpacing: "0.5px",
    cursor: "pointer",
    fontFamily: "Georgia, serif",
    boxShadow: "0 6px 20px rgba(13,33,55,0.3)",
  },
  btnSecondary: {
    width: "100%",
    padding: "14px",
    marginBottom: "10px",
    border: "none",
    borderRadius: "12px",
    background: COLORS.white,
    color: COLORS.navy,
    fontSize: "14px",
    fontWeight: "600",
    cursor: "pointer",
    fontFamily: "Georgia, serif",
    boxShadow: "0 3px 12px rgba(13,33,55,0.1)",
    display: "flex",
    alignItems: "center",
    gap: "12px",
    textAlign: "left",
    border: `1.5px solid rgba(13,33,55,0.08)`,
  },
  btnIcon: {
    width: "36px",
    height: "36px",
    borderRadius: "10px",
    display: "flex",
    alignItems: "center",
    justifyContent: "center",
    fontSize: "18px",
    flexShrink: 0,
  },
  navbar: {
    background: `linear-gradient(135deg, ${COLORS.navy} 0%, ${COLORS.navyLight} 100%)`,
    display: "flex",
    flexShrink: 0,
    borderTop: "1px solid rgba(255,255,255,0.08)",
  },
  navBtn: {
    flex: 1,
    background: "none",
    border: "none",
    color: "rgba(255,255,255,0.5)",
    padding: "12px 6px",
    fontSize: "10px",
    fontFamily: "Georgia, serif",
    cursor: "pointer",
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
    gap: "4px",
    letterSpacing: "0.5px",
    transition: "color 0.2s",
  },
  navBtnActive: {
    color: COLORS.gold,
  },
  navIcon: { fontSize: "20px" },
  alertCard: {
    borderRadius: "14px",
    padding: "16px",
    marginBottom: "12px",
    border: "1.5px solid",
  },
  tag: {
    display: "inline-block",
    padding: "3px 10px",
    borderRadius: "20px",
    fontSize: "10px",
    fontWeight: "700",
    letterSpacing: "1px",
    textTransform: "uppercase",
    marginBottom: "8px",
  },
  divider: {
    height: "1px",
    background: `linear-gradient(90deg, transparent, ${COLORS.creamDark}, transparent)`,
    margin: "16px 0",
  },
  statRow: {
    display: "flex",
    gap: "10px",
    marginBottom: "14px",
  },
  statBox: {
    flex: 1,
    background: COLORS.white,
    borderRadius: "12px",
    padding: "14px 10px",
    textAlign: "center",
    boxShadow: "0 3px 10px rgba(13,33,55,0.07)",
  },
  statNum: {
    fontSize: "22px",
    fontWeight: "700",
    color: COLORS.navy,
  },
  statLabel: {
    fontSize: "10px",
    color: COLORS.textMid,
    letterSpacing: "0.5px",
    marginTop: "2px",
  },
  checkItem: {
    display: "flex",
    alignItems: "center",
    gap: "10px",
    padding: "8px 0",
    borderBottom: `1px solid ${COLORS.creamDark}`,
    fontSize: "13px",
    color: COLORS.textDark,
  },
  quizOption: {
    width: "100%",
    padding: "14px 16px",
    marginBottom: "10px",
    border: `1.5px solid ${COLORS.creamDark}`,
    borderRadius: "12px",
    background: COLORS.white,
    color: COLORS.textDark,
    fontSize: "14px",
    cursor: "pointer",
    fontFamily: "Georgia, serif",
    textAlign: "left",
    transition: "all 0.15s",
  },
};

const QUIZ = [
  {
    q: "A flood is approaching. What should you grab first?",
    options: ["Water & documents", "TV remote", "Extra clothes", "Pet toys"],
    correct: 0,
    explanation: "Water and important documents are survival priorities during a flood.",
  },
  {
    q: "You smell gas in your home. What do you do?",
    options: ["Open windows only", "Leave immediately, don't use switches", "Call 911 from inside", "Turn on fans"],
    correct: 1,
    explanation: "Any spark can ignite gas. Leave immediately without touching electrical switches.",
  },
  {
    q: "During a tornado, the safest place is:",
    options: ["Near windows to watch", "Top floor interior room", "Basement or interior room", "In your car"],
    correct: 2,
    explanation: "Get as low as possible in an interior room away from windows.",
  },
];

export default function EvacuAID() {
  const [screen, setScreen] = useState("onboard");
  const [activeNav, setActiveNav] = useState("home");
  const [user, setUser] = useState({ zip: "", people: "", pets: "", access: "" });
  const [checks, setChecks] = useState({});
  const [quizStep, setQuizStep] = useState(0);
  const [quizScore, setQuizScore] = useState(0);
  const [quizDone, setQuizDone] = useState(false);
  const [quizFeedback, setQuizFeedback] = useState(null);

  const navigate = (nav) => {
    setActiveNav(nav);
    setScreen(nav);
  };

  const startApp = () => {
    if (!user.zip) return;
    setScreen("home");
    setActiveNav("home");
  };

  const supplies = [
    "Water (1 gallon/person/day × 3 days)",
    "Non-perishable food (3-day supply)",
    "Flashlight & extra batteries",
    "First aid kit",
    "Portable phone charger",
    "Important documents (copies)",
    "Cash in small bills",
    "Whistle to signal for help",
    user.pets === "yes" ? "Pet food & carrier" : null,
    user.access ? "Medications & medical supplies" : null,
  ].filter(Boolean);

  const answerQuiz = (idx) => {
    const correct = idx === QUIZ[quizStep].correct;
    setQuizFeedback({ correct, explanation: QUIZ[quizStep].explanation });
    if (correct) setQuizScore((s) => s + 1);
    setTimeout(() => {
      setQuizFeedback(null);
      if (quizStep + 1 >= QUIZ.length) setQuizDone(true);
      else setQuizStep((s) => s + 1);
    }, 1800);
  };

  return (
    <div style={styles.shell}>
      <div style={styles.phone}>
        {/* HEADER */}
        <div style={styles.header}>
          <div>
            <div style={styles.headerTitle}>🛡 EvacuAID</div>
            <div style={styles.headerSub}>Emergency Preparedness</div>
          </div>
          <div style={{ textAlign: "right" }}>
            <div style={{ color: COLORS.gold, fontSize: "11px", fontWeight: "700" }}>● LIVE</div>
            <div style={{ color: "rgba(255,255,255,0.5)", fontSize: "10px", marginTop: "2px" }}>
              {user.zip || "No ZIP set"}
            </div>
          </div>
        </div>

        {/* ALERT BANNER */}
        <div style={styles.alertBanner}>⚠ Active Emergency Alerts in Your Area</div>

        {/* CONTENT */}
        <div style={styles.content}>

          {/* ONBOARDING */}
          {screen === "onboard" && (
            <>
              <div style={styles.pageTitle}>Welcome</div>
              <div style={styles.pageSubtitle}>Let's personalize your emergency plan</div>
              <div style={styles.card}>
                <label style={styles.label}>ZIP Code</label>
                <input style={styles.input} placeholder="e.g. 75075" value={user.zip}
                  onChange={(e) => setUser({ ...user, zip: e.target.value })} />
                <label style={styles.label}>Household Size</label>
                <input style={styles.input} placeholder="e.g. 4 people" value={user.people}
                  onChange={(e) => setUser({ ...user, people: e.target.value })} />
                <label style={styles.label}>Pets?</label>
                <input style={styles.input} placeholder="yes / no" value={user.pets}
                  onChange={(e) => setUser({ ...user, pets: e.target.value })} />
                <label style={styles.label}>Accessibility Needs</label>
                <input style={styles.input} placeholder="e.g. wheelchair, none" value={user.access}
                  onChange={(e) => setUser({ ...user, access: e.target.value })} />
                <button style={styles.btnPrimary} onClick={startApp}>Start EvacuAID →</button>
              </div>
            </>
          )}

          {/* HOME DASHBOARD */}
          {screen === "home" && (
            <>
              <div style={styles.pageTitle}>Dashboard</div>
              <div style={styles.pageSubtitle}>Your emergency command center</div>
              <div style={styles.statRow}>
                <div style={styles.statBox}>
                  <div style={styles.statNum}>{user.people || "—"}</div>
                  <div style={styles.statLabel}>People</div>
                </div>
                <div style={styles.statBox}>
                  <div style={styles.statNum}>{user.pets === "yes" ? "🐾" : "—"}</div>
                  <div style={styles.statLabel}>Pets</div>
                </div>
                <div style={styles.statBox}>
                  <div style={styles.statNum}>{user.zip || "—"}</div>
                  <div style={styles.statLabel}>ZIP</div>
                </div>
              </div>
              {[
                { icon: "🎒", label: "Emergency Supplies", sub: `${supplies.length} items to prepare`, color: "#E8F4FD", screen: "supplies" },
                { icon: "🏠", label: "Find Shelter", sub: "Nearest locations near you", color: "#FEF3E2", screen: "shelter" },
                { icon: "📋", label: "Emergency Plan", sub: "Your personalized checklist", color: "#E8F8F0", screen: "plan" },
                { icon: "🎓", label: "Training Quiz", sub: "Test your readiness", color: "#FDE8E8", screen: "training" },
              ].map((item) => (
                <button key={item.screen} style={styles.btnSecondary} onClick={() => setScreen(item.screen)}>
                  <div style={{ ...styles.btnIcon, background: item.color }}>{item.icon}</div>
                  <div>
                    <div style={{ fontWeight: "700", fontSize: "14px" }}>{item.label}</div>
                    <div style={{ fontSize: "11px", color: COLORS.textMid, marginTop: "2px" }}>{item.sub}</div>
                  </div>
                  <div style={{ marginLeft: "auto", color: COLORS.textMid, fontSize: "16px" }}>›</div>
                </button>
              ))}
            </>
          )}

          {/* ALERTS */}
          {screen === "alerts" && (
            <>
              <div style={styles.pageTitle}>Active Alerts</div>
              <div style={styles.pageSubtitle}>Real-time emergency notifications</div>
              {[
                { type: "WARNING", title: "Tornado Warning", desc: "Seek shelter in a basement or interior room immediately. Avoid windows.", color: COLORS.red, bg: "#FEF0EF" },
                { type: "WATCH", title: "Flood Watch", desc: "Avoid low-elevation roads. Move valuables to higher ground.", color: "#E67E22", bg: "#FEF9F0" },
                { type: "ADVISORY", title: "High Winds", desc: "Gusts up to 55 mph expected. Secure outdoor objects.", color: COLORS.sky, bg: "#EFF7FD" },
              ].map((a) => (
                <div key={a.title} style={{ ...styles.alertCard, borderColor: a.color, background: a.bg }}>
                  <div style={{ ...styles.tag, background: a.color, color: "white" }}>{a.type}</div>
                  <div style={{ fontWeight: "700", fontSize: "15px", color: COLORS.navy, marginBottom: "6px" }}>{a.title}</div>
                  <div style={{ fontSize: "13px", color: COLORS.textMid, lineHeight: "1.5" }}>{a.desc}</div>
                </div>
              ))}
            </>
          )}

          {/* SUPPLIES */}
          {screen === "supplies" && (
            <>
              <button style={{ ...styles.btnSecondary, width: "auto", marginBottom: "16px", padding: "8px 14px" }}
                onClick={() => setScreen("home")}>← Back</button>
              <div style={styles.pageTitle}>Emergency Supplies</div>
              <div style={styles.pageSubtitle}>Customized for your household</div>
              <div style={styles.card}>
                {supplies.map((item, i) => (
                  <div key={i} style={styles.checkItem}>
                    <span style={{ fontSize: "18px", cursor: "pointer" }} onClick={() => setChecks(c => ({ ...c, [i]: !c[i] }))}>
                      {checks[i] ? "✅" : "⬜"}
                    </span>
                    <span style={{ textDecoration: checks[i] ? "line-through" : "none", color: checks[i] ? COLORS.textMid : COLORS.textDark }}>
                      {item}
                    </span>
                  </div>
                ))}
              </div>
              <div style={{ ...styles.card, textAlign: "center", background: COLORS.navy }}>
                <div style={{ color: COLORS.gold, fontSize: "20px", fontWeight: "700" }}>
                  {Object.values(checks).filter(Boolean).length} / {supplies.length}
                </div>
                <div style={{ color: "rgba(255,255,255,0.7)", fontSize: "12px", marginTop: "4px" }}>items packed</div>
              </div>
            </>
          )}

          {/* SHELTER */}
          {screen === "shelter" && (
            <>
              <button style={{ ...styles.btnSecondary, width: "auto", marginBottom: "16px", padding: "8px 14px" }}
                onClick={() => setScreen("home")}>← Back</button>
              <div style={styles.pageTitle}>Nearby Shelters</div>
              <div style={styles.pageSubtitle}>Based on ZIP: {user.zip}</div>
              {[
                { name: "Red Cross Emergency Shelter", addr: "1200 Main St", dist: "2.4 mi", open: true },
                { name: "Community Recreation Center", addr: "450 Oak Ave", dist: "4.7 mi", open: true },
                { name: "Lincoln High School Gym", addr: "800 Lincoln Blvd", dist: "6.1 mi", open: false },
              ].map((s) => (
                <div key={s.name} style={styles.card}>
                  <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start" }}>
                    <div>
                      <div style={{ fontWeight: "700", fontSize: "14px", color: COLORS.navy }}>{s.name}</div>
                      <div style={{ fontSize: "12px", color: COLORS.textMid, marginTop: "4px" }}>{s.addr}</div>
                    </div>
                    <div style={{ ...styles.tag, background: s.open ? "#E8F8F0" : "#FEF0EF", color: s.open ? "#27AE60" : COLORS.red, border: "none", whiteSpace: "nowrap" }}>
                      {s.open ? "● Open" : "● Closed"}
                    </div>
                  </div>
                  <div style={styles.divider} />
                  <div style={{ display: "flex", justifyContent: "space-between", fontSize: "12px", color: COLORS.textMid }}>
                    <span>📍 {s.dist} away</span>
                    <span style={{ color: COLORS.sky, fontWeight: "600", cursor: "pointer" }}>Get Directions →</span>
                  </div>
                </div>
              ))}
            </>
          )}

          {/* PLAN */}
          {screen === "plan" && (
            <>
              <button style={{ ...styles.btnSecondary, width: "auto", marginBottom: "16px", padding: "8px 14px" }}
                onClick={() => setScreen("home")}>← Back</button>
              <div style={styles.pageTitle}>Your Plan</div>
              <div style={styles.pageSubtitle}>Personalized for your household</div>
              <div style={styles.card}>
                <div style={{ display: "flex", gap: "8px", flexWrap: "wrap" }}>
                  {[`👥 ${user.people || "?"}`, user.pets === "yes" ? "🐾 Pets" : null, user.access ? `♿ ${user.access}` : null].filter(Boolean).map(t => (
                    <div key={t} style={{ ...styles.tag, background: "#E8F0FD", color: COLORS.navy, border: "1px solid #C5D8F5" }}>{t}</div>
                  ))}
                </div>
                <div style={styles.divider} />
                <div style={{ fontWeight: "700", fontSize: "13px", color: COLORS.navy, marginBottom: "10px", letterSpacing: "0.5px" }}>ACTION CHECKLIST</div>
                {[
                  "Pack emergency supply kit",
                  "Identify two evacuation routes",
                  "Save emergency contacts offline",
                  "Locate nearest shelter",
                  "Charge backup power banks",
                  user.pets === "yes" ? "Arrange pet carrier & food" : null,
                  user.access ? "Pack medications & medical equipment" : null,
                ].filter(Boolean).map((item, i) => (
                  <div key={i} style={styles.checkItem}>
                    <span style={{ fontSize: "16px", color: COLORS.sky }}>○</span>
                    <span style={{ fontSize: "13px" }}>{item}</span>
                  </div>
                ))}
              </div>
            </>
          )}

          {/* TRAINING */}
          {screen === "training" && (
            <>
              <button style={{ ...styles.btnSecondary, width: "auto", marginBottom: "16px", padding: "8px 14px" }}
                onClick={() => { setScreen("home"); setQuizStep(0); setQuizScore(0); setQuizDone(false); setQuizFeedback(null); }}>← Back</button>
              <div style={styles.pageTitle}>Training Quiz</div>
              <div style={styles.pageSubtitle}>Test your emergency readiness</div>
              {quizDone ? (
                <div style={{ ...styles.card, textAlign: "center" }}>
                  <div style={{ fontSize: "48px", marginBottom: "12px" }}>{quizScore === QUIZ.length ? "🏆" : quizScore >= 2 ? "👍" : "📚"}</div>
                  <div style={{ fontSize: "28px", fontWeight: "700", color: COLORS.navy }}>{quizScore}/{QUIZ.length}</div>
                  <div style={{ color: COLORS.textMid, marginTop: "8px", fontSize: "14px" }}>
                    {quizScore === QUIZ.length ? "Perfect score! You're ready." : "Good effort — review and try again."}
                  </div>
                  <button style={{ ...styles.btnPrimary, marginTop: "20px" }}
                    onClick={() => { setQuizStep(0); setQuizScore(0); setQuizDone(false); }}>Retake Quiz</button>
                </div>
              ) : (
                <>
                  <div style={{ ...styles.card, background: COLORS.navy, marginBottom: "16px" }}>
                    <div style={{ color: COLORS.gold, fontSize: "11px", letterSpacing: "1px", marginBottom: "8px" }}>
                      QUESTION {quizStep + 1} OF {QUIZ.length}
                    </div>
                    <div style={{ color: "white", fontSize: "15px", lineHeight: "1.5", fontWeight: "600" }}>
                      {QUIZ[quizStep].q}
                    </div>
                  </div>
                  {quizFeedback ? (
                    <div style={{ ...styles.card, background: quizFeedback.correct ? "#E8F8F0" : "#FEF0EF", border: `2px solid ${quizFeedback.correct ? "#27AE60" : COLORS.red}`, textAlign: "center" }}>
                      <div style={{ fontSize: "28px" }}>{quizFeedback.correct ? "✅" : "❌"}</div>
                      <div style={{ fontWeight: "700", color: quizFeedback.correct ? "#27AE60" : COLORS.red, marginTop: "8px" }}>
                        {quizFeedback.correct ? "Correct!" : "Not quite."}
                      </div>
                      <div style={{ fontSize: "13px", color: COLORS.textMid, marginTop: "8px", lineHeight: "1.5" }}>{quizFeedback.explanation}</div>
                    </div>
                  ) : (
                    QUIZ[quizStep].options.map((opt, i) => (
                      <button key={i} style={styles.quizOption} onClick={() => answerQuiz(i)}>{opt}</button>
                    ))
                  )}
                </>
              )}
            </>
          )}
        </div>

        {/* NAVBAR */}
        {screen !== "onboard" && (
          <div style={styles.navbar}>
            {[
              { id: "home", icon: "🏠", label: "Home" },
              { id: "alerts", icon: "🚨", label: "Alerts" },
              { id: "training", icon: "🎓", label: "Training" },
            ].map((n) => (
              <button key={n.id} style={{ ...styles.navBtn, ...(activeNav === n.id ? styles.navBtnActive : {}) }}
                onClick={() => navigate(n.id)}>
                <span style={styles.navIcon}>{n.icon}</span>
                {n.label}
              </button>
            ))}
          </div>
        )}
      </div>
    </div>
  );
}
