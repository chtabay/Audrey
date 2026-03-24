# Roadmap

<style>
:root {
  --rm-done: #4caf50;
  --rm-progress: #ff9800;
  --rm-todo: #607d8b;
  --rm-blocked: #9e9e9e;
  --rm-future: #37474f;
  --rm-bg-card: #263238;
  --rm-bg-phase: #1a2327;
  --rm-text: #eceff1;
  --rm-text-dim: #90a4ae;
  --rm-border: #37474f;
  --rm-accent: #ffc107;
}
[data-md-color-scheme="default"] {
  --rm-bg-card: #ffffff;
  --rm-bg-phase: #f5f7f9;
  --rm-text: #263238;
  --rm-text-dim: #607d8b;
  --rm-border: #cfd8dc;
  --rm-future: #b0bec5;
}

.rm-overview {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 12px;
  margin: 24px 0 32px;
}
.rm-stat {
  text-align: center;
  padding: 16px 8px;
  border-radius: 10px;
  background: var(--rm-bg-card);
  border: 1px solid var(--rm-border);
}
.rm-stat-num {
  font-size: 2rem;
  font-weight: 800;
  line-height: 1;
}
.rm-stat-label {
  font-size: .75rem;
  text-transform: uppercase;
  letter-spacing: .08em;
  color: var(--rm-text-dim);
  margin-top: 4px;
}

.rm-global-bar {
  height: 10px;
  border-radius: 5px;
  background: var(--rm-border);
  overflow: hidden;
  margin-bottom: 32px;
  display: flex;
}
.rm-global-bar span {
  height: 100%;
  transition: width .6s ease;
}
.rm-bar-done { background: var(--rm-done); }
.rm-bar-progress { background: var(--rm-progress); }
.rm-bar-todo { background: var(--rm-todo); }

.rm-phase {
  background: var(--rm-bg-phase);
  border: 1px solid var(--rm-border);
  border-radius: 12px;
  padding: 20px 24px 16px;
  margin-bottom: 24px;
}
.rm-phase-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 12px;
}
.rm-phase-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--rm-text);
  margin: 0;
}
.rm-phase-badge {
  font-size: .7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: .06em;
  padding: 3px 10px;
  border-radius: 20px;
  color: #fff;
}
.rm-phase-bar {
  height: 6px;
  border-radius: 3px;
  background: var(--rm-border);
  overflow: hidden;
  margin-bottom: 16px;
}
.rm-phase-bar-fill {
  height: 100%;
  border-radius: 3px;
  transition: width .6s ease;
}

.rm-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 12px;
}
.rm-card {
  background: var(--rm-bg-card);
  border: 1px solid var(--rm-border);
  border-radius: 8px;
  padding: 14px 16px;
  display: flex;
  flex-direction: column;
  gap: 6px;
  position: relative;
  overflow: hidden;
  transition: border-color .2s;
}
.rm-card:hover {
  border-color: var(--rm-accent);
}
.rm-card::before {
  content: "";
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 4px;
}
.rm-card.done::before { background: var(--rm-done); }
.rm-card.progress::before { background: var(--rm-progress); }
.rm-card.todo::before { background: var(--rm-todo); }
.rm-card.blocked::before { background: var(--rm-blocked); }
.rm-card.future::before { background: var(--rm-future); }

.rm-card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
}
.rm-card-id {
  font-family: 'JetBrains Mono', monospace;
  font-size: .7rem;
  color: var(--rm-text-dim);
  background: var(--rm-bg-phase);
  padding: 2px 6px;
  border-radius: 4px;
}
.rm-card-status {
  font-size: .65rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: .06em;
  padding: 2px 8px;
  border-radius: 10px;
  color: #fff;
  white-space: nowrap;
}
.rm-card-title {
  font-weight: 600;
  font-size: .92rem;
  color: var(--rm-text);
  margin: 2px 0;
}
.rm-card-desc {
  font-size: .78rem;
  color: var(--rm-text-dim);
  line-height: 1.4;
}
.rm-card-link {
  font-size: .75rem;
  margin-top: auto;
}
.rm-card-dep {
  font-size: .7rem;
  color: var(--rm-text-dim);
  font-style: italic;
}

.s-done { background: var(--rm-done); }
.s-progress { background: var(--rm-progress); }
.s-todo { background: var(--rm-todo); }
.s-blocked { background: var(--rm-blocked); }
.s-future { background: var(--rm-future); }

.rm-legend {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin: 24px 0 8px;
  font-size: .8rem;
}
.rm-legend-item {
  display: flex;
  align-items: center;
  gap: 6px;
}
.rm-legend-dot {
  width: 12px;
  height: 12px;
  border-radius: 3px;
  flex-shrink: 0;
}
</style>

<div class="rm-overview" markdown>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-done)">6</div>
    <div class="rm-stat-label">Terminés</div>
  </div>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-progress)">0</div>
    <div class="rm-stat-label">En cours</div>
  </div>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-todo)">5</div>
    <div class="rm-stat-label">À faire</div>
  </div>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-blocked)">4</div>
    <div class="rm-stat-label">Bloqués</div>
  </div>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-future)">8</div>
    <div class="rm-stat-label">À venir</div>
  </div>
  <div class="rm-stat">
    <div class="rm-stat-num" style="color:var(--rm-accent)">23</div>
    <div class="rm-stat-label">Total livrables</div>
  </div>
</div>

<div class="rm-global-bar">
  <span class="rm-bar-done" style="width:26%"></span>
  <span class="rm-bar-progress" style="width:0%"></span>
  <span class="rm-bar-todo" style="width:22%"></span>
</div>

<div class="rm-legend">
  <span class="rm-legend-item"><span class="rm-legend-dot s-done"></span> Terminé</span>
  <span class="rm-legend-item"><span class="rm-legend-dot s-progress"></span> En cours</span>
  <span class="rm-legend-item"><span class="rm-legend-dot s-todo"></span> À faire</span>
  <span class="rm-legend-item"><span class="rm-legend-dot s-blocked"></span> Bloqué / En attente</span>
  <span class="rm-legend-item"><span class="rm-legend-dot s-future"></span> À venir</span>
</div>

---

<!-- ═══════════════ PHASE 1 ═══════════════ -->

<div class="rm-phase">
  <div class="rm-phase-header">
    <div class="rm-phase-title">Phase 1 — Études & Analyses</div>
    <span class="rm-phase-badge s-done">6 / 6 — Terminée</span>
  </div>
  <div class="rm-phase-bar"><div class="rm-phase-bar-fill" style="width:100%;background:var(--rm-done)"></div></div>
  <div class="rm-cards">

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">B1-B4</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Étude de marché</div>
    <div class="rm-card-desc">Offre, demande, benchmark prix, profils locataires, SWOT emplacement. Loyer médian : 170 €/mois.</div>
    <div class="rm-card-link"><a href="marche.md">→ Marché & Demande</a></div>
  </div>

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">B3</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Zone de chalandise</div>
    <div class="rm-card-desc">Isochrone 15 min, 133 000 hab., 5 515 établissements. Score faisabilité : 3,9 / 5.</div>
    <div class="rm-card-link"><a href="marche.md#zone-de-chalandise">→ Zone de chalandise</a></div>
  </div>

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">E1-E3</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Cadre juridique des baux</div>
    <div class="rm-card-desc">Comparatif bail commercial / dérogatoire / précaire. Recommandation : 3-6-9 étage, dérogatoire RDC.</div>
    <div class="rm-card-link"><a href="juridique.md">→ Juridique — Baux</a></div>
  </div>

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">A1-A4</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Urbanisme, ERP & PMR</div>
    <div class="rm-card-desc">Procédure DP, normes ERP 5e cat., dérogation PMR étage, diagnostics obligatoires.</div>
    <div class="rm-card-link"><a href="urbanisme.md">→ Urbanisme & ERP</a></div>
  </div>

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">D1-D5</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Business Plan financier</div>
    <div class="rm-card-desc">Prévisionnel 3 ans, cash-flow -138 €/mois, enrichissement ~5 %/an, vision 20 ans.</div>
    <div class="rm-card-link"><a href="business-plan.md">→ Business Plan</a></div>
  </div>

  <div class="rm-card done">
    <div class="rm-card-top">
      <span class="rm-card-id">COM</span>
      <span class="rm-card-status s-done">Terminé</span>
    </div>
    <div class="rm-card-title">Stratégie de commercialisation</div>
    <div class="rm-card-desc">Tarifs, canaux, argumentaires, sélection locataires, calendrier T-6 à T+6.</div>
    <div class="rm-card-link"><a href="commercialisation.md">→ Commercialisation</a></div>
  </div>

  </div>
</div>

<!-- ═══════════════ PHASE 2 ═══════════════ -->

<div class="rm-phase">
  <div class="rm-phase-header">
    <div class="rm-phase-title">Phase 2 — Validations terrain</div>
    <span class="rm-phase-badge s-todo">0 / 5 — À lancer</span>
  </div>
  <div class="rm-phase-bar"><div class="rm-phase-bar-fill" style="width:0%;background:var(--rm-todo)"></div></div>
  <div class="rm-cards">

  <div class="rm-card todo">
    <div class="rm-card-top">
      <span class="rm-card-id">A1</span>
      <span class="rm-card-status s-todo">À faire</span>
    </div>
    <div class="rm-card-title">Périmètre de mixité fonctionnelle</div>
    <div class="rm-card-desc">Vérifier auprès de la mairie si la parcelle est dans le périmètre autorisant le commerce de détail au RDC.</div>
  </div>

  <div class="rm-card todo">
    <div class="rm-card-top">
      <span class="rm-card-id">A2</span>
      <span class="rm-card-status s-todo">À faire</span>
    </div>
    <div class="rm-card-title">Diagnostic amiante (DAAT)</div>
    <div class="rm-card-desc">Commander le diagnostic amiante avant travaux. Bâtiment années 70-75, obligatoire avant 1997.</div>
  </div>

  <div class="rm-card todo">
    <div class="rm-card-top">
      <span class="rm-card-id">A3</span>
      <span class="rm-card-status s-todo">À faire</span>
    </div>
    <div class="rm-card-title">RDV service urbanisme</div>
    <div class="rm-card-desc">Rendez-vous informel pour valider la compatibilité du projet avec la zone UMv1.</div>
  </div>

  <div class="rm-card todo">
    <div class="rm-card-top">
      <span class="rm-card-id">B1</span>
      <span class="rm-card-status s-blocked">Bloqué</span>
    </div>
    <div class="rm-card-title">Qualification destination RDC</div>
    <div class="rm-card-desc">Choisir la destination officielle du RDC (bureau, services, commerce). Impact PLU + ERP + baux.</div>
    <div class="rm-card-dep">Dépend de : A1, A3</div>
  </div>

  <div class="rm-card todo">
    <div class="rm-card-top">
      <span class="rm-card-id">B2</span>
      <span class="rm-card-status s-todo">À faire</span>
    </div>
    <div class="rm-card-title">Référence cadastrale</div>
    <div class="rm-card-desc">Identifier la parcelle exacte via cadastre.gouv.fr. Nécessaire pour le dossier de DP (CERFA 13703).</div>
  </div>

  </div>
</div>

<!-- ═══════════════ PHASE 3 ═══════════════ -->

<div class="rm-phase">
  <div class="rm-phase-header">
    <div class="rm-phase-title">Phase 3 — Dossiers administratifs</div>
    <span class="rm-phase-badge s-blocked">0 / 4 — En attente</span>
  </div>
  <div class="rm-phase-bar"><div class="rm-phase-bar-fill" style="width:0%;background:var(--rm-blocked)"></div></div>
  <div class="rm-cards">

  <div class="rm-card blocked">
    <div class="rm-card-top">
      <span class="rm-card-id">C1</span>
      <span class="rm-card-status s-blocked">Bloqué</span>
    </div>
    <div class="rm-card-title">Déclaration Préalable (DP)</div>
    <div class="rm-card-desc">CERFA 13703 + plans, notice descriptive. Instruction : 1 mois. Changement habitation → bureau/commerce.</div>
    <div class="rm-card-dep">Dépend de : A3, B1, B2</div>
  </div>

  <div class="rm-card blocked">
    <div class="rm-card-top">
      <span class="rm-card-id">C2</span>
      <span class="rm-card-status s-blocked">Bloqué</span>
    </div>
    <div class="rm-card-title">Dossier ERP</div>
    <div class="rm-card-desc">CERFA 13824*04 — demande d'autorisation de construire, d'aménager ou de modifier un ERP.</div>
    <div class="rm-card-dep">Dépend de : C1</div>
  </div>

  <div class="rm-card blocked">
    <div class="rm-card-top">
      <span class="rm-card-id">C3</span>
      <span class="rm-card-status s-blocked">Bloqué</span>
    </div>
    <div class="rm-card-title">Consultation avocat baux</div>
    <div class="rm-card-desc">Faire valider la stratégie bail commercial (étage) + dérogatoire (RDC), clauses clés, articulation Projet P.</div>
    <div class="rm-card-dep">Dépend de : B1</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">C4</span>
      <span class="rm-card-status s-future">À planifier</span>
    </div>
    <div class="rm-card-title">Consultation expert-comptable</div>
    <div class="rm-card-desc">Choisir la structure juridique (nom propre / SCI IS / SCI IR) et l'option TVA selon les locataires retenus.</div>
  </div>

  </div>
</div>

<!-- ═══════════════ PHASE 4 ═══════════════ -->

<div class="rm-phase">
  <div class="rm-phase-header">
    <div class="rm-phase-title">Phase 4 — Travaux</div>
    <span class="rm-phase-badge s-future">0 / 4 — À venir</span>
  </div>
  <div class="rm-phase-bar"><div class="rm-phase-bar-fill" style="width:0%;background:var(--rm-future)"></div></div>
  <div class="rm-cards">

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">T0</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Plans d'aménagement définitifs</div>
    <div class="rm-card-desc">Plans cotés RDC + étage, circulation, conformité PMR, issues de secours. Validation architecte.</div>
    <div class="rm-card-dep">Dépend de : C1, C2</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">T1</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Phase 1 — PAC, électricité, normes</div>
    <div class="rm-card-desc">Remplacement chaudière fioul → PAC, mise aux normes électriques NF C 15-100, compteurs.</div>
    <div class="rm-card-dep">Dépend de : T0, A2 (amiante)</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">T2</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Phase 2 — Cloisonnement, sanitaires, sols</div>
    <div class="rm-card-desc">3 bureaux étage, cloisons, 3 WC, 2 kitchenettes, 1 douche, revêtements de sols.</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">T3</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Phase 3 — Finitions & peinture</div>
    <div class="rm-card-desc">Peinture, menuiseries intérieures, signalétique, derniers raccordements.</div>
  </div>

  </div>
</div>

<!-- ═══════════════ PHASE 5 ═══════════════ -->

<div class="rm-phase">
  <div class="rm-phase-header">
    <div class="rm-phase-title">Phase 5 — Commercialisation & Ouverture</div>
    <span class="rm-phase-badge s-future">0 / 4 — À venir</span>
  </div>
  <div class="rm-phase-bar"><div class="rm-phase-bar-fill" style="width:0%;background:var(--rm-future)"></div></div>
  <div class="rm-cards">

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">M1</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Rédaction des baux</div>
    <div class="rm-card-desc">Bail commercial 3-6-9 (étage) et bail dérogatoire (RDC), rédigés par avocat.</div>
    <div class="rm-card-dep">Dépend de : C3</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">M2</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Annonces & prospection</div>
    <div class="rm-card-desc">BureauxLocaux, LeBonCoin Pro, prospection directe soignants locaux, panneau sur site. Démarrer T-6 mois.</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">M3</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Sélection locataires</div>
    <div class="rm-card-desc">Dossier de candidature, visites, scoring solvabilité, signature.</div>
  </div>

  <div class="rm-card future">
    <div class="rm-card-top">
      <span class="rm-card-id">M4</span>
      <span class="rm-card-status s-future">À venir</span>
    </div>
    <div class="rm-card-title">Ouverture — Premiers locataires</div>
    <div class="rm-card-desc">État des lieux d'entrée, remise des clés, démarrage des loyers. Objectif : début-milieu 2027.</div>
  </div>

  </div>
</div>

---

*Dernière mise à jour : 23/03/2026*

[← Retour à l'accueil](index.md)
