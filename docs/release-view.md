# Release View

<style>
:root {
  --rv-done: #4caf50;
  --rv-progress: #42a5f5;
  --rv-waiting: #ff9800;
  --rv-blocked: #ef5350;
  --rv-planned: #78909c;
  --rv-bg-card: rgba(255,255,255,0.04);
  --rv-bg-phase: rgba(255,255,255,0.02);
  --rv-border: rgba(255,255,255,0.08);
  --rv-text: #cfd8dc;
  --rv-text-dim: #90a4ae;
  --rv-tag-urba: #ab47bc;
  --rv-tag-marche: #29b6f6;
  --rv-tag-juridique: #ffa726;
  --rv-tag-finance: #66bb6a;
  --rv-tag-travaux: #ef5350;
  --rv-tag-commercial: #ec407a;
  --rv-tag-projet-p: #8d6e63;
}
[data-md-color-scheme="default"] {
  --rv-bg-card: rgba(0,0,0,0.03);
  --rv-bg-phase: rgba(0,0,0,0.01);
  --rv-border: rgba(0,0,0,0.10);
  --rv-text: #37474f;
  --rv-text-dim: #78909c;
}

.rv-hero {
  text-align: center;
  padding: 1.5rem 1rem 1rem;
  margin-bottom: 1.5rem;
}
.rv-hero h2 {
  font-size: 1rem;
  font-weight: 400;
  color: var(--rv-text-dim);
  margin: 0 0 1.2rem;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

.rv-stats {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
  margin-bottom: 0.5rem;
}
.rv-stat {
  text-align: center;
}
.rv-stat-value {
  font-size: 2rem;
  font-weight: 700;
  line-height: 1.1;
  color: var(--rv-text);
}
.rv-stat-value.done { color: var(--rv-done); }
.rv-stat-value.progress { color: var(--rv-progress); }
.rv-stat-value.waiting { color: var(--rv-waiting); }
.rv-stat-value.planned { color: var(--rv-planned); }
.rv-stat-label {
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--rv-text-dim);
  margin-top: 0.2rem;
}

.rv-global-bar {
  max-width: 600px;
  margin: 1.5rem auto 0;
  height: 10px;
  border-radius: 5px;
  background: var(--rv-border);
  overflow: hidden;
  display: flex;
}
.rv-global-bar .seg-done { background: var(--rv-done); }
.rv-global-bar .seg-progress { background: var(--rv-progress); }
.rv-global-bar .seg-waiting { background: var(--rv-waiting); }
.rv-global-bar .seg-planned { background: var(--rv-planned); }

.rv-pipeline {
  display: flex;
  gap: 1rem;
  overflow-x: auto;
  padding: 0.5rem 0 1.5rem;
  scroll-snap-type: x mandatory;
}
.rv-phase {
  flex: 0 0 280px;
  min-width: 280px;
  scroll-snap-align: start;
  background: var(--rv-bg-phase);
  border: 1px solid var(--rv-border);
  border-radius: 12px;
  padding: 1rem;
}
.rv-phase-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 0.8rem;
  padding-bottom: 0.6rem;
  border-bottom: 1px solid var(--rv-border);
}
.rv-phase-title {
  font-size: 0.85rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--rv-text);
}
.rv-phase-count {
  font-size: 0.7rem;
  color: var(--rv-text-dim);
  background: var(--rv-border);
  padding: 2px 8px;
  border-radius: 10px;
}
.rv-phase-bar {
  height: 4px;
  border-radius: 2px;
  background: var(--rv-border);
  margin-bottom: 0.8rem;
  overflow: hidden;
}
.rv-phase-bar-fill {
  height: 100%;
  border-radius: 2px;
  transition: width 0.6s ease;
}

.rv-card {
  background: var(--rv-bg-card);
  border: 1px solid var(--rv-border);
  border-radius: 8px;
  padding: 0.7rem 0.8rem;
  margin-bottom: 0.5rem;
  transition: border-color 0.2s;
}
.rv-card:hover {
  border-color: var(--rv-progress);
}
.rv-card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 0.35rem;
}
.rv-card-title {
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--rv-text);
  line-height: 1.3;
}
.rv-card-status {
  flex-shrink: 0;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-left: 8px;
}
.rv-card-status.done { background: var(--rv-done); box-shadow: 0 0 6px rgba(76,175,80,0.5); }
.rv-card-status.progress { background: var(--rv-progress); box-shadow: 0 0 6px rgba(66,165,245,0.5); animation: rv-pulse 2s infinite; }
.rv-card-status.waiting { background: var(--rv-waiting); }
.rv-card-status.blocked { background: var(--rv-blocked); }
.rv-card-status.planned { background: var(--rv-planned); }
@keyframes rv-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}
.rv-card-meta {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  flex-wrap: wrap;
}
.rv-tag {
  font-size: 0.62rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  padding: 1px 6px;
  border-radius: 3px;
  color: #fff;
}
.rv-tag.urba { background: var(--rv-tag-urba); }
.rv-tag.marche { background: var(--rv-tag-marche); }
.rv-tag.juridique { background: var(--rv-tag-juridique); }
.rv-tag.finance { background: var(--rv-tag-finance); }
.rv-tag.travaux { background: var(--rv-tag-travaux); }
.rv-tag.commercial { background: var(--rv-tag-commercial); }
.rv-tag.projet-p { background: var(--rv-tag-projet-p); }
.rv-card-link {
  font-size: 0.65rem;
  color: var(--rv-text-dim);
  margin-left: auto;
}
.rv-card-link a {
  color: var(--rv-progress);
  text-decoration: none;
}
.rv-card-link a:hover { text-decoration: underline; }

.rv-card-bar {
  height: 3px;
  border-radius: 2px;
  background: var(--rv-border);
  margin-top: 0.5rem;
  overflow: hidden;
}
.rv-card-bar-fill {
  height: 100%;
  border-radius: 2px;
}

.rv-legend {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
  margin-top: 1.5rem;
  padding-top: 1rem;
  border-top: 1px solid var(--rv-border);
}
.rv-legend-item {
  display: flex;
  align-items: center;
  gap: 0.35rem;
  font-size: 0.72rem;
  color: var(--rv-text-dim);
}
.rv-legend-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}

@media (max-width: 768px) {
  .rv-phase { flex: 0 0 85vw; min-width: 85vw; }
  .rv-stats { gap: 1rem; }
  .rv-stat-value { font-size: 1.5rem; }
}
</style>

<div class="rv-hero" markdown>

## Suivi des livrables — Maison Castel

<div class="rv-stats">
  <div class="rv-stat">
    <div class="rv-stat-value done">8</div>
    <div class="rv-stat-label">Terminés</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value progress">3</div>
    <div class="rv-stat-label">En cours</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value waiting">5</div>
    <div class="rv-stat-label">En attente</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value planned">13</div>
    <div class="rv-stat-label">Planifiés</div>
  </div>
</div>

<div class="rv-global-bar">
  <div class="seg-done" style="width:27.6%"></div>
  <div class="seg-progress" style="width:10.3%"></div>
  <div class="seg-waiting" style="width:17.2%"></div>
  <div class="seg-planned" style="width:44.9%"></div>
</div>

</div>

---

<div class="rv-pipeline">

<!-- ========== PHASE 1 : ÉTUDES ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">1 · Études</span>
    <span class="rv-phase-count">6 / 6</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Étude de marché locale</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag marche">Marché</span>
      <span class="rv-card-link"><a href="../marche/">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Zone de chalandise & scoring</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag marche">Marché</span>
      <span class="rv-card-link"><a href="../marche/#zone-de-chalandise">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Cadre juridique des baux</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag juridique">Juridique</span>
      <span class="rv-card-link"><a href="../juridique/">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Analyse urbanisme, ERP, PMR</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
      <span class="rv-card-link"><a href="../urbanisme/">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Business Plan financier</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag finance">Finance</span>
      <span class="rv-card-link"><a href="../business-plan/">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Stratégie de commercialisation</span>
      <span class="rv-card-status done"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
      <span class="rv-card-link"><a href="../commercialisation/">voir →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:100%; background:var(--rv-done)"></div></div>
  </div>

</div>

<!-- ========== PHASE 2 : AUTORISATIONS ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">2 · Autorisations</span>
    <span class="rv-phase-count">0 / 7</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:0%; background:var(--rv-progress)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Vérifier périmètre de mixité fonctionnelle</span>
      <span class="rv-card-status progress"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
      <span class="rv-card-link"><a href="../plan-actions/#priorite-1-immediat-cette-semaine">actions →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:10%; background:var(--rv-progress)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Diagnostic amiante (DAAT)</span>
      <span class="rv-card-status progress"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag travaux">Travaux</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:5%; background:var(--rv-progress)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">RDV informel urbanisme mairie</span>
      <span class="rv-card-status progress"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:5%; background:var(--rv-progress)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Qualification destination RDC</span>
      <span class="rv-card-status waiting"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
      <span class="rv-tag juridique">Juridique</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-waiting)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Référence cadastrale</span>
      <span class="rv-card-status waiting"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-waiting)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Déclaration Préalable (DP)</span>
      <span class="rv-card-status waiting"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-waiting)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Dossier ERP (CERFA 13824)</span>
      <span class="rv-card-status waiting"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag urba">Urbanisme</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-waiting)"></div></div>
  </div>

</div>

<!-- ========== PHASE 3 : MONTAGE ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">3 · Montage</span>
    <span class="rv-phase-count">0 / 5</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Consultation avocat baux commerciaux</span>
      <span class="rv-card-status waiting"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag juridique">Juridique</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-waiting)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Consultation expert-comptable</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Choix structure juridique</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag juridique">Juridique</span>
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Décision option TVA</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Financement travaux 85 k€</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

</div>

<!-- ========== PHASE 4 : TRAVAUX ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">4 · Travaux</span>
    <span class="rv-phase-count">0 / 4</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Plans d'aménagement définitifs</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag travaux">Travaux</span>
      <span class="rv-tag urba">Urbanisme</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Phase 1 — PAC + électricité</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag travaux">Travaux</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Phase 2 — Cloisons, sanitaires, sols</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag travaux">Travaux</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Phase 3 — Finitions</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag travaux">Travaux</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

</div>

<!-- ========== PHASE 5 : COMMERCIALISATION ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">5 · Mise en marché</span>
    <span class="rv-phase-count">0 / 4</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Rédaction & diffusion annonces</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
      <span class="rv-card-link"><a href="../commercialisation/">plan →</a></span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Prospection directe (soignants, consultants)</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Sélection & validation locataires</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
      <span class="rv-tag juridique">Juridique</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Signature baux</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag juridique">Juridique</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

</div>

<!-- ========== PHASE 6 : EXPLOITATION ========== -->
<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">6 · Exploitation</span>
    <span class="rv-phase-count">0 / 3</span>
  </div>
  <div class="rv-phase-bar"><div class="rv-phase-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Ouverture étage — Projet C</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Ouverture RDC — bail dérogatoire</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag commercial">Commercial</span>
      <span class="rv-tag projet-p">Projet P</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

  <div class="rv-card">
    <div class="rv-card-top">
      <span class="rv-card-title">Suivi gestion & reporting</span>
      <span class="rv-card-status planned"></span>
    </div>
    <div class="rv-card-meta">
      <span class="rv-tag finance">Finance</span>
    </div>
    <div class="rv-card-bar"><div class="rv-card-bar-fill" style="width:0%; background:var(--rv-planned)"></div></div>
  </div>

</div>

</div>

<!-- LEGEND -->
<div class="rv-legend">
  <div class="rv-legend-item"><div class="rv-legend-dot" style="background:var(--rv-done)"></div> Terminé</div>
  <div class="rv-legend-item"><div class="rv-legend-dot" style="background:var(--rv-progress)"></div> En cours</div>
  <div class="rv-legend-item"><div class="rv-legend-dot" style="background:var(--rv-waiting)"></div> En attente</div>
  <div class="rv-legend-item"><div class="rv-legend-dot" style="background:var(--rv-planned)"></div> Planifié</div>
</div>

---

## Dépendances entre phases

```
  ┌────────────┐    ┌──────────────┐    ┌─────────┐    ┌──────────────┐    ┌──────────────┐
  │ 1. ÉTUDES  │───▶│2. AUTORISATIONS│──▶│3. MONTAGE│──▶│  4. TRAVAUX  │──▶│ 6. EXPLOIT.  │
  │  (terminé) │    │  (en cours)    │   │(planifié)│   │  (planifié)  │   │  (planifié)  │
  └────────────┘    └──────────────┘    └─────────┘    └──────┬───────┘    └──────────────┘
                                                               │                    ▲
                                                               │  ┌──────────────┐  │
                                                               └─▶│5. MISE EN    │──┘
                                                                  │   MARCHÉ     │
                                                                  │  (T-6 mois)  │
                                                                  └──────────────┘
```

!!! tip "Chemin critique"
    **Autorisations → Travaux → Ouverture.** Le périmètre de mixité fonctionnelle (phase 2) conditionne la qualification du RDC et donc la Déclaration Préalable. La commercialisation (phase 5) démarre **pendant** les travaux, 4-6 mois avant l'ouverture.

!!! note "Mise à jour"
    Cette vue reflète l'état du projet au **23 mars 2026**. Les compteurs et barres de progression sont à mettre à jour manuellement dans le fichier `docs/release-view.md` au fur et à mesure de l'avancement.

---

[← Retour à l'accueil](index.md)
