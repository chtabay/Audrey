# Release View

<style>
:root {
  --rv-done: #4caf50;
  --rv-progress: #2196f3;
  --rv-planned: #607d8b;
  --rv-blocked: #ff9800;
  --rv-card-bg: #1a2332;
  --rv-card-border: #2a3a4e;
  --rv-text: #e0e6ed;
  --rv-text-muted: #8899aa;
  --rv-track-bg: #0d1520;
  --rv-header-bg: #0f1923;
}

[data-md-color-scheme="default"] {
  --rv-card-bg: #f5f7fa;
  --rv-card-border: #dce1e8;
  --rv-text: #1a2332;
  --rv-text-muted: #607d8b;
  --rv-track-bg: #ebeef2;
  --rv-header-bg: #e8ecf0;
}

.rv-container { max-width: 960px; margin: 0 auto; }

.rv-phase {
  margin-bottom: 2.5rem;
  border: 1px solid var(--rv-card-border);
  border-radius: 8px;
  overflow: hidden;
  background: var(--rv-card-bg);
}

.rv-phase-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 1.5rem;
  background: var(--rv-header-bg);
  border-bottom: 1px solid var(--rv-card-border);
}

.rv-phase-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--rv-text);
  letter-spacing: 0.03em;
}

.rv-phase-meta {
  display: flex;
  align-items: center;
  gap: 1rem;
  font-size: 0.8rem;
  color: var(--rv-text-muted);
}

.rv-badge {
  display: inline-block;
  padding: 0.2rem 0.7rem;
  border-radius: 3px;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #fff;
}
.rv-badge--done { background: var(--rv-done); }
.rv-badge--progress { background: var(--rv-progress); }
.rv-badge--planned { background: var(--rv-planned); }
.rv-badge--blocked { background: var(--rv-blocked); }

.rv-progress-bar {
  width: 100%;
  height: 4px;
  background: var(--rv-track-bg);
  overflow: hidden;
}
.rv-progress-bar > span {
  display: block;
  height: 100%;
  transition: width 0.6s ease;
}
.rv-progress-bar > span.done { background: var(--rv-done); }
.rv-progress-bar > span.progress { background: var(--rv-progress); }
.rv-progress-bar > span.planned { background: var(--rv-planned); }

.rv-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1px;
  background: var(--rv-card-border);
}
@media (max-width: 600px) { .rv-cards { grid-template-columns: 1fr; } }

.rv-card {
  padding: 0.9rem 1.2rem;
  background: var(--rv-card-bg);
  display: flex;
  align-items: flex-start;
  gap: 0.7rem;
}

.rv-icon {
  flex-shrink: 0;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  margin-top: 2px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.65rem;
  color: #fff;
  font-weight: 700;
}
.rv-icon--done { background: var(--rv-done); }
.rv-icon--progress { background: var(--rv-progress); }
.rv-icon--planned { background: var(--rv-planned); }
.rv-icon--blocked { background: var(--rv-blocked); }

.rv-card-body { flex: 1; min-width: 0; }

.rv-card-title {
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--rv-text);
  line-height: 1.3;
}

.rv-card-sub {
  font-size: 0.75rem;
  color: var(--rv-text-muted);
  margin-top: 0.15rem;
}

.rv-card-dep {
  font-size: 0.7rem;
  color: var(--rv-blocked);
  margin-top: 0.2rem;
  font-style: italic;
}

.rv-legend {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  margin-bottom: 2rem;
  font-size: 0.8rem;
  color: var(--rv-text-muted);
}
.rv-legend-item {
  display: flex;
  align-items: center;
  gap: 0.4rem;
}
.rv-legend-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.rv-summary {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  margin-bottom: 2.5rem;
  text-align: center;
}
@media (max-width: 600px) { .rv-summary { grid-template-columns: repeat(2, 1fr); } }

.rv-stat {
  padding: 1rem;
  border-radius: 8px;
  background: var(--rv-card-bg);
  border: 1px solid var(--rv-card-border);
}
.rv-stat-value {
  font-size: 1.8rem;
  font-weight: 800;
  line-height: 1;
}
.rv-stat-label {
  font-size: 0.75rem;
  color: var(--rv-text-muted);
  margin-top: 0.3rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
</style>

<div class="rv-container" markdown>

<div class="rv-summary">
  <div class="rv-stat">
    <div class="rv-stat-value" style="color: var(--rv-done);">6</div>
    <div class="rv-stat-label">Livrés</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value" style="color: var(--rv-progress);">0</div>
    <div class="rv-stat-label">En cours</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value" style="color: var(--rv-blocked);">5</div>
    <div class="rv-stat-label">En attente</div>
  </div>
  <div class="rv-stat">
    <div class="rv-stat-value" style="color: var(--rv-planned);">16</div>
    <div class="rv-stat-label">Planifiés</div>
  </div>
</div>

<div class="rv-legend">
  <span class="rv-legend-item"><span class="rv-legend-dot" style="background:var(--rv-done)"></span> Livré</span>
  <span class="rv-legend-item"><span class="rv-legend-dot" style="background:var(--rv-progress)"></span> En cours</span>
  <span class="rv-legend-item"><span class="rv-legend-dot" style="background:var(--rv-blocked)"></span> En attente / Bloqué</span>
  <span class="rv-legend-item"><span class="rv-legend-dot" style="background:var(--rv-planned)"></span> Planifié</span>
</div>

<!-- ============================================================ -->
<!-- ALPHA 0.1                                                     -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">ALPHA 0.1 — Études & Analyses</span>
    <div class="rv-phase-meta">
      <span>Mars 2026</span>
      <span class="rv-badge rv-badge--done">LIVRÉ</span>
      <span>6 / 6</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="done" style="width:100%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Étude de marché locale</div>
        <div class="rv-card-sub">Offre, demande, benchmark prix, SWOT</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Zone de chalandise</div>
        <div class="rv-card-sub">133k hab., scoring 3.9/5, délai 3-8 mois</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Cadre juridique des baux</div>
        <div class="rv-card-sub">Commercial 3-6-9 vs dérogatoire vs précaire</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Urbanisme, ERP & PMR</div>
        <div class="rv-card-sub">PLU UMv1, DP, 5e catégorie, dérogation PMR</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Business Plan financier</div>
        <div class="rv-card-sub">Prévisionnel 3 ans, fiscalité, vision 20 ans</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--done">✓</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Stratégie de commercialisation</div>
        <div class="rv-card-sub">Tarifs, canaux, calendrier opérationnel</div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ -->
<!-- ALPHA 0.2                                                     -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">ALPHA 0.2 — Validations terrain</span>
    <div class="rv-phase-meta">
      <span>Avr — Mai 2026</span>
      <span class="rv-badge rv-badge--blocked">EN ATTENTE</span>
      <span>0 / 5</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="planned" style="width:0%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--blocked">!</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Périmètre de mixité fonctionnelle</div>
        <div class="rv-card-sub">Confirmation mairie — détermine le RDC</div>
        <div class="rv-card-dep">Bloquant pour Projet P</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--blocked">!</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Diagnostic amiante (DAAT)</div>
        <div class="rv-card-sub">Obligatoire avant travaux — bâtiment avant 1997</div>
        <div class="rv-card-dep">Bloquant pour les travaux</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--blocked">!</span>
      <div class="rv-card-body">
        <div class="rv-card-title">RDV service urbanisme</div>
        <div class="rv-card-sub">Valider la compatibilité du projet avec le PLU</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Référence cadastrale</div>
        <div class="rv-card-sub">cadastre.gouv.fr ou acte de vente</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Qualification destination RDC</div>
        <div class="rv-card-sub">Bureau / services / commerce de détail</div>
        <div class="rv-card-dep">Dépend de : Périmètre mixité + RDV urbanisme</div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ -->
<!-- BETA 1.0                                                      -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">BETA 1.0 — Autorisations & Conseil</span>
    <div class="rv-phase-meta">
      <span>Mai — Juil 2026</span>
      <span class="rv-badge rv-badge--planned">PLANIFIÉ</span>
      <span>0 / 5</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="planned" style="width:0%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Déclaration Préalable</div>
        <div class="rv-card-sub">CERFA 13703 — instruction 1 mois</div>
        <div class="rv-card-dep">Dépend de : ALPHA 0.2 complet</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Dossier ERP</div>
        <div class="rv-card-sub">CERFA 13824*04 — commission sécurité</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Consultation avocat baux</div>
        <div class="rv-card-sub">Clauses, stratégie bail commercial + dérogatoire</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Consultation expert-comptable</div>
        <div class="rv-card-sub">Structure juridique, option TVA, régime fiscal</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Décision option TVA</div>
        <div class="rv-card-sub">~7 800 € récupérables si locataires assujettis</div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ -->
<!-- BETA 2.0                                                      -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">BETA 2.0 — Travaux</span>
    <div class="rv-phase-meta">
      <span>Juil — Déc 2026</span>
      <span class="rv-badge rv-badge--planned">PLANIFIÉ</span>
      <span>0 / 5</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="planned" style="width:0%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Phase 1 — Gros œuvre technique</div>
        <div class="rv-card-sub">PAC, électricité complète, mise aux normes</div>
        <div class="rv-card-dep">Dépend de : DP accordée + DAAT clean</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Phase 2 — Aménagement intérieur</div>
        <div class="rv-card-sub">Cloisonnement, sanitaires, sols, peinture</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Phase 3 — Finitions</div>
        <div class="rv-card-sub">Kitchenettes, douche, équipements</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Vérification conformité ERP</div>
        <div class="rv-card-sub">Issues de secours, extincteurs, signalétique</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">DPE après travaux</div>
        <div class="rv-card-sub">Impact PAC sur la performance énergétique</div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ -->
<!-- RC 1.0                                                        -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">RC 1.0 — Commercialisation</span>
    <div class="rv-phase-meta">
      <span>Oct 2026 — Fév 2027</span>
      <span class="rv-badge rv-badge--planned">PLANIFIÉ</span>
      <span>0 / 3</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="planned" style="width:0%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Lancement annonces & prospection</div>
        <div class="rv-card-sub">BureauxLocaux, LeBonCoin Pro, panneau, mailing soignants</div>
        <div class="rv-card-dep">Démarrer T-4 à T-6 mois avant ouverture</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Visites & sélection locataires</div>
        <div class="rv-card-sub">Dossiers, solvabilité, compatibilité activité</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Rédaction & signature des baux</div>
        <div class="rv-card-sub">Baux commerciaux (étage) + dérogatoire (RDC)</div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ -->
<!-- RELEASE 1.0                                                   -->
<!-- ============================================================ -->

<div class="rv-phase">
  <div class="rv-phase-header">
    <span class="rv-phase-title">RELEASE 1.0 — Exploitation</span>
    <div class="rv-phase-meta">
      <span>Début — Mi 2027</span>
      <span class="rv-badge rv-badge--planned">PLANIFIÉ</span>
      <span>0 / 3</span>
    </div>
  </div>
  <div class="rv-progress-bar"><span class="planned" style="width:0%"></span></div>
  <div class="rv-cards">
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Ouverture bureaux étage — Projet C</div>
        <div class="rv-card-sub">3 bureaux de 17 m², bail commercial, 170 €/mois</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Premier locataire RDC</div>
        <div class="rv-card-sub">Bail dérogatoire, 450 €/mois, max 3 ans</div>
      </div>
    </div>
    <div class="rv-card">
      <span class="rv-icon rv-icon--planned">—</span>
      <div class="rv-card-body">
        <div class="rv-card-title">Gestion courante activée</div>
        <div class="rv-card-sub">~2-4h/mois, gestion directe recommandée</div>
      </div>
    </div>
  </div>
</div>

---

*Dernière mise à jour : 23 mars 2026* · [← Retour à l'accueil](index.md)

</div>
