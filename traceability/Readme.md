# Traceability Matrices

This section presents the traceability matrices for the PDP-O competency questions. The matrices link each competency question to its reasoning type, use case source, ontology classes covered, SPARQL query, and expected PDP-O answer.

---

## Traceability Matrix for Enhanced Reasoning CQs

| CQ ID | Reasoning Type | Use Case Source | Classes Covered | SPARQL Query Abbreviated | Expected Answer from PDP-O |
| --- | --- | --- | --- | --- | --- |
| Sub1 | Subsumption | Agricultural expert needs to list all infectious diseases for quarantine purposes. | Plant_Disease, Infectious_Plant_Disease, Pathogen | `SELECT DISTINCT ?disease WHERE { ?disease rdf:type dp:Infectious_Plant_Disease . }` | Bayoud_Disease<br>Fusarium_Wilt_Disease<br>Inflorescence_Rot_Disease<br>Black_Scorch_Disease<br>Diplodia_Leaf-Base_Disease<br>Graphiola_Leaf_Spot_Disease<br>Ganoderma_Butt_Rot_Disease<br>Anthracnose_Disease_Of_Date_Palm<br>Reddish_Brown_Parallel_Spot_Disease<br>Pestalotia_Leaf_Spot_Disease<br>Shole_Hole_Disease_Of_Date_Palm<br>Rectangular_Pale_Brown_Spot_Disease<br>Brown_Leaf_Spot_Disease<br>Rachis_Blight_Of_Date_Palm<br>Root_Rot_Of_Date_Palm<br>Fruit_Rot_Disease_Of_Date_Palm<br>Al-Wijam_Disease<br>Brittle_Leaves_Disease<br>Lethal_Yellowing_Disease |
| Sub2 | Subsumption | Farmer observes fungal symptoms and wants to know which diseases are caused by fungi. | Plant_Disease, Plant_Fungi_Disease, Fungi | `SELECT DISTINCT ?disease WHERE { ?disease rdf:type dp:Plant_Fungi_Disease . }` | Bayoud_Disease<br>Fusarium_Wilt_Disease<br>Inflorescence_Rot_Disease<br>Black_Scorch_Disease<br>Diplodia_Leaf-Base_Disease<br>Graphiola_Leaf_Spot_Disease<br>Ganoderma_Butt_Rot_Disease<br>Anthracnose_Disease_Of_Date_Palm<br>Reddish_Brown_Parallel_Spot_Disease<br>Pestalotia_Leaf_Spot_Disease<br>Shole_Hole_Disease_Of_Date_Palm<br>Rectangular_Pale_Brown_Spot_Disease<br>Brown_Leaf_Spot_Disease<br>Rachis_Blight_Of_Date_Palm<br>Root_Rot_Of_Date_Palm<br>Fruit_Rot_Disease_Of_Date_Palm |
| Sub3 | Subsumption | Agronomist needs to identify abiotic, non-infectious diseases for environmental stress analysis. | Plant_Disease, Noninfectious_Plant_Disease, Abiotic_Causal_Agent | `SELECT DISTINCT ?disease WHERE { ?disease rdf:type dp:Noninfectious_Plant_Disease . }` | Frost_Damage<br>Hail_Damage<br>Heat_Damage<br>Water_Stress<br>Wind_Damage<br>Quick_Wilting_Of_Date_Palm<br>Physiological_Yellowing_Of_Date_Palm_Leaf |
| Sub4 | Subsumption | Policy maker wants to list all date palm diseases caused by any pathogen. | Plant_Disease, Infectious_Plant_Disease, Host_Plant, Date_Palm | `SELECT DISTINCT ?disease WHERE { ?disease rdf:type dp:Infectious_Plant_Disease . ?disease dp:is_Disease_Of dp:Date_Palm . }` | Bayoud_Disease<br>Fusarium_Wilt_Disease<br>Inflorescence_Rot_Disease<br>Black_Scorch_Disease<br>Diplodia_Leaf-Base_Disease<br>Graphiola_Leaf_Spot_Disease<br>Ganoderma_Butt_Rot_Disease<br>Anthracnose_Disease_Of_Date_Palm<br>Reddish_Brown_Parallel_Spot_Disease<br>Pestalotia_Leaf_Spot_Disease<br>Shole_Hole_Disease_Of_Date_Palm<br>Rectangular_Pale_Brown_Spot_Disease<br>Brown_Leaf_Spot_Disease<br>Rachis_Blight_Of_Date_Palm<br>Root_Rot_Of_Date_Palm<br>Fruit_Rot_Disease_Of_Date_Palm<br>Al-Wijam_Disease<br>Brittle_Leaves_Disease<br>Lethal_Yellowing_Disease |
| Prop1 | Property hierarchy | Researcher needs all symptoms that appear on leaf rachis, including those asserted via sub-properties such as `first_Appears_On` and `finally_Appears_On`. | Symptom, Plant_Part, Leaf_Rachis, is_Appear_On | `SELECT DISTINCT ?symptom WHERE { ?symptom dp:is_Appear_On dp:Leaf_Rachis . }` | Dark_Brown_Stripe_On_Leaf_Rachis<br>Yellowish_Brown_Stripe_On_Leaf_Base_And_Leaf_Rachis<br>Subepidermal_Spots_On_Both_sides_Of_Leaflet_and_Rachis<br>Dark_Gray_Spot_With_Reddish_To_Brown_Edges<br>Light_Brown_Spot_With_Dark_Brown_Edges_On_Leaflet<br>Small_Yellow_Or_Brown_Circular_Spot_On_Leaflet_And_Leaf_Rachis<br>Sticky_Material_At_Entrance_Holes_On_Leaf_Rachis<br>Tunnels_At_Leaf_Rachis |
| Prop2 | Property hierarchy | Farmer wants all recommended control methods for Fusarium wilt, including chemical, cultural, and biological controls. | Plant_Disease, Control_Method, has_Recommended_Control | `SELECT DISTINCT ?control WHERE { dp:Fusarium_Wilt_Disease dp:has_Recommended_Control ?control . }` | Sodium_Hypochlorite<br>Agricultural_Quarantine<br>Avoid_excessive_Irrigation<br>Stop_Planting_In_The_Same_Site<br>Stop_Planting_Of_Hijazi_Alfalfa<br>Uprooted_And_Burned_Of_Infected_Palms_On_The_Spot<br>Use_Of_Thermal_Sterilization<br>Methyl_Bromide |
| Prop3 | Property hierarchy | Pest control officer wants pest damages that have any chemical control using the super-property. | Pest_Damage, Control_Method, Chemical_Control, has_Recommended_Control | `SELECT DISTINCT ?damage WHERE { ?damage dp:has_Recommended_Control ?control . ?control rdf:type dp:Chemical_Control . }` | Red_Palm_Weevil |
| Prop4 | Property hierarchy and subsumption | Entomologist needs symptoms appearing on any part of the leaf, including leaflet, rachis, base, etc., using the general property `is_Appear_On`. | Symptom, Plant_Part, Leaf, is_Appear_On | `SELECT DISTINCT ?symptom WHERE { ?symptom dp:is_Appear_On ?part . ?part rdfs:subClassOf dp:Leaf . }` | Leaf_Become_Yellow<br>Wilting_On_One_Side_Of_Leaf<br>Leaf_Become_Ash_Grey<br>Death_Of_Leaflet_From_the_Tip_Backwards<br>Leaf_Become_Yellow_White_On_One_Side<br>Breakage_Or_Gradual_Drying_Of_Leaf<br>Circular_Or_Irregular_Scorched_Shot_Holes_On_Leaf_Edge<br>Death_Of_Leaflet_Tip<br>Early_Death_Of_Old_Palm_Trees_Leaf<br>Large_Dark_Brown_Or_Black_Spot_On_Green_Leaf<br>Leaf_Breakage_And_Drooping_Then_Dry_Up<br>Leaf_Dry_Up_One_After_The_Other_Until_The_Tree_Has_Died<br>Leaf_Hangs_Down_Along_The_Trunk<br>Leaf_Resembling_Wet_Feathers_Appearance<br>Small_Parallel_Reddish_Brown_Spot_On_Leaf<br>Spot_Become_Pale_With_Reddish_Brown_Edges_On_Dying_Leaf<br>Superficial_And_Deep_Tunnels_On_Green_Leaf<br>Wilting_Of_Leaf |
| Inv1 | Inverse | Farmer observes “Wilting on one side of leaf” and wants to know which disease or pest it indicates using the inverse of `has_Symptom`. | Symptom, Plant_Disease, Pest_Damage, indicates | `SELECT DISTINCT ?problem WHERE { dp:Wilting_On_One_Side_Of_Leaf dp:indicates ?problem . }` | Bayoud_Disease<br>Fusarium_Wilt_Disease |
| Inv2 | Inverse | Plant pathologist sees “White powdery covering on inflorescence” and asks what causal agent is responsible through an inverse chain. | Symptom, Plant_Disease, Causal_Agent, indicates, is_Caused_By | `SELECT DISTINCT ?agent WHERE { dp:Inflorescences_Covered_With_White_Powdery dp:indicates ?problem . ?problem dp:is_Caused_By ?agent . }` | Mauginiella_Scattae |
| Inv3 | Inverse and subsumption | Researcher wants all symptoms that indicate any fungal disease. | Symptom, Plant_Fungi_Disease, indicates | `SELECT DISTINCT ?symptom WHERE { ?symptom dp:indicates ?disease . ?disease rdf:type dp:Plant_Fungi_Disease . }` | Dark_Brown_Stripe_On_Leaf_Rachis<br>Inflorescences_Covered_With_White_Powdery<br>Leaf_With_Scorched_Or_Charcoal_Like_Appearance<br>Brown_Or_Rusty_Spots<br>Drying_Of_Inflorescence<br>Rot_Of_Flowers_And_Spikelets<br>Leaf_Become_Ash_Grey<br>Leaf_Resembling_Wet_Feathers_Appearance |
| Trans1 | Transitivity | Botanist asks for all plant parts that are part of the leaf directly or indirectly. | Plant_Part, Leaf, is_Part_Of | `SELECT DISTINCT ?part WHERE { ?part dp:is_Part_Of dp:Leaf . }` | Leaf_Blade<br>Petiole<br>Leaf_Sheath<br>Leaf_Base<br>Leaf_Rachis<br>Leaflet<br>Leaf_Spine<br>Leaflet_Margin<br>Centre_Leaves |
| Trans2 | Transitivity | Diagnostician asks: if a symptom appears on leaflet, what larger plant parts are affected through the part-whole chain? | Symptom, Plant_Part, Leaflet, Leaf, is_Appear_On, is_Part_Of | `SELECT DISTINCT ?part WHERE { ?symptom dp:is_Appear_On dp:Leaflet . dp:Leaflet dp:is_Part_Of ?part . }` | Leaf_Blade<br>Leaf |
| Trans3 | Transitivity and property | Extension officer needs all symptoms that affect the whole leaf by being on any sub-part. | Symptom, Plant_Part, Leaf, is_Appear_On, is_Part_Of | `SELECT DISTINCT ?symptom WHERE { ?symptom dp:is_Appear_On ?subpart . ?subpart dp:is_Part_Of dp:Leaf . }` | Wilting_On_One_Side_Of_Leaf<br>Leaf_Become_Yellow<br>Brown_Spot_With_Light_Center_And_Dark_Edge_Surrounded_By_Yellow_Halo_On_Leaflet<br>Death_Of_Leaflet_From_the_Tip_Backwards<br>Death_Of_Leaflet_Tip<br>Deformation_Of_Leaves<br>Leaf_Become_Powdery<br>Leaf_Breakage_And_Drooping_Then_Dry_Up<br>Leaf_Dry_Up_One_After_The_Other_Until_The_Tree_Has_Died<br>Malformation_And_Twisting_Of_Leaf<br>Sticky_Material_At_Entrance_Holes_On_Leaf_Rachis<br>Tunnels_At_Leaf_Rachis |
| SWRL1 | SWRL Rule 17 | Pathologist wants all symptoms of Inflorescence rot disease that are inferred via Rule 17 from `is_Effect_Of`. | Plant_Disease, Causal_Agent, Symptom, is_Effect_Of, has_Symptom | `SELECT DISTINCT ?symptom WHERE { dp:Inflorescence_Rot_Disease dp:has_Symptom ?symptom . }` | Brown_Or_Rusty_Spots<br>Inflorescences_Covered_With_White_Powdery<br>Partial_Or_Complete_Destruction_Of_Flowers_And_Spikelets<br>Rot_Of_Flowers_And_Spikelets<br>Drying_Of_Inflorescence<br>Rot_Of_Young_Green_Fruit<br><br>Note: `Rot_Of_Young_Green_Fruit` is inferred from `is_Effect_Of` of `Mauginiella_Scattae`. |
| SWRL2 | SWRL Rule 17 | Researcher wants diseases that have a symptom which is also an effect of their causal agent. | Plant_Disease, Causal_Agent, Symptom, is_Effect_Of, has_Symptom, is_Caused_By | `SELECT DISTINCT ?disease WHERE { ?disease dp:has_Symptom ?sym . ?sym dp:is_Effect_Of ?agent . ?disease dp:is_Caused_By ?agent . }` | Bayoud_Disease<br>Fusarium_Wilt_Disease<br>Inflorescence_Rot_Disease<br>Black_Scorch_Disease<br>Diplodia_Leaf-Base_Disease<br>Graphiola_Leaf_Spot_Disease<br>Ganoderma_Butt_Rot_Disease |
| SWRL3 | SWRL Rule 18 | Entomologist asks for pest damages that have symptoms inferred via Rule 18. | Pest_Damage, Causal_Agent, Symptom, is_Effect_Of, has_Symptom, is_Caused_By | `SELECT DISTINCT ?damage WHERE { ?damage dp:has_Symptom ?sym . ?sym dp:is_Effect_Of ?agent . ?damage dp:is_Caused_By ?agent . ?damage rdf:type dp:Pest_Damage . }` | Red_Palm_Weevil_Damage |
| SWRL4 | SWRL Rule 18 | Farmer sees “Oozing of brownish fluid with typical fermented odor” on Red palm weevil damage and asks for the causal agent. | Pest_Damage, Causal_Agent, Symptom, is_Effect_Of, has_Symptom | `SELECT DISTINCT ?agent WHERE { dp:Red_Palm_Weevil_Damage dp:has_Symptom dp:Oozing_Of_Brownish_Fluid_With_Typical_Fermented_Odor . dp:Oozing_Of_Brownish_Fluid_With_Typical_Fermented_Odor dp:is_Effect_Of ?agent . }` | Rhynchophorus_Ferrugineus |
| SWRL5 | SWRL Rules | Plant health specialist wants all symptoms, both directly asserted and inferred via rules, for Black scorch disease. | Plant_Disease, Symptom, has_Symptom | `SELECT DISTINCT ?symptom WHERE { dp:Black_Scorch_Disease dp:has_Symptom ?symptom . }` | Black_Rot_On_Inflorescence<br>Dark_Brown_Or_Black_Hard_Lesions_On_Leaf<br>Death_Of_Leaflet_From_the_Tip_Backwards<br>Diminishes_Growth_Of_New_Leaf<br>Inflorescence_Blight<br>Leaf_With_Scorched_Or_Charcoal_Like_Appearance<br>Malformation_And_Twisting_Of_Leaf<br>Root_Rot<br>Round_To_Oblong_Dark_Brown_Spots<br>Terminal_Bud_Rot_And_Blackening<br>Trunk_Rot |
| SWRL6 | SWRL Rules | Diagnostician wants different diseases or pests that share the same inferred symptom to distinguish similar cases. | Plant_Disease, Pest_Damage, Symptom, has_Symptom | `SELECT DISTINCT ?p1 ?p2 ?s WHERE { ?p1 dp:has_Symptom ?s . ?p2 dp:has_Symptom ?s . FILTER(?p1 != ?p2) }` | Bayoud_Disease and Fusarium_Wilt_Disease share Wilting_On_One_Side_Of_Leaf<br>Bayoud_Disease and Reddish_Brown_Parallel_Spot_Disease share Dark_Brown_Stripe_On_Leaf_Rachis<br>Date_Palm_Dubas_Bug and Mealy_Bugs share Black_Sooty_Rot<br>Red_Palm_Weevil_Damage and Fusarium_Wilt_Disease share Wilting_Of_Leaf |

---

## Traceability Matrix for 90 CQs

| CQ ID | Category | Use Case Source |
| --- | --- | --- |
| Disease/Pest CQ1 | Disease/Pest | Farmer reports ejection of chewed fibers from trunk and yellowing leaves/offshoots. |
| Disease/Pest CQ2 | Disease/Pest | Farmer sees cylindrical holes and brown sticky material on trunk/leaf base. |
| Disease/Pest CQ3 | Disease/Pest | Farmer observes dark brown stripe on dorsal side of leaf rachis. |
| Disease/Pest CQ4 | Disease/Pest | Farmer sees brown/rusty spots and white powdery covering on unopened inflorescence. |
| Disease/Pest CQ5 | Disease/Pest | Farmer finds longitudinal tunnels/holes on fruit bunch, silver spikelet tips, and holes on unopened spathe. |
| Disease/Pest CQ6 | Disease/Pest | Farmer reports leaflets become light green/yellowish green and honeydew oozing. |
| Disease/Pest CQ7 | Disease/Pest | Farmer sees yellowish-brown stripe on leaf base/rachis, leaf base rot, and death of offshoot. |
| Disease/Pest CQ8 | Disease/Pest | Farmer observes leaf deformation and brown spots with yellow halo on leaflet. |
| Disease/Pest CQ9 | Disease/Pest | Farmer reports pale spots with brown ring and circular/irregular scorched shot holes on leaf edge. |
| Disease/Pest CQ10 | Disease/Pest | Farmer finds sticky material at entrance holes, tunnels on leaf rachis, and powdery leaf. |
| Disease/Pest CQ11 | Disease/Pest | Farmer sees death of leaflet from tip backwards, leaf malformation, and scorched/charcoal appearance. |
| Disease/Pest CQ12 | Disease/Pest | Farmer reports subepidermal spots, yellow pustules turning black, and leaf drying. |
| Disease/Pest CQ13 | Disease/Pest | Farmer sees leaflet tip/edges burnt grey and small yellow/brown circular spots. |
| Disease/Pest CQ14 | Disease/Pest | Farmer finds small shotgun-like holes and ejection of wooden sawdust from trunk/leaf base. |
| Disease/Pest CQ15 | Disease/Pest | Farmer reports small dried fruit hanging by silken threads, dropped fruit with holes, and fruit turns dark red. |
| Disease/Pest CQ16 | Disease/Pest | Farmer sees deep tunnels on fruit stalk, superficial/deep tunnels on green leaves, and offshoot leaf twisting. |
| Disease/Pest CQ17 | Disease/Pest | Farmer observes wilting on one side of leaf and dark brown stripe on leaf rachis. |
| Disease/Pest CQ18 | Disease/Pest | Farmer reports small parallel reddish-brown spots on leaf and dark brown stripe on rachis. |
| Disease/Pest CQ19 | Disease/Pest | Farmer finds small holes below inflorescence spathe and inflorescences devoid of flowers/fruits. |
| Disease/Pest CQ20 | Disease/Pest | Farmer sees honeydew oozing on leaflet and fruit deformation/curl. |
| Disease/Pest CQ21 | Disease/Pest | Farmer reports palm tissue becomes light green with brown spots and fruit deformation/curl. |
| Disease/Pest CQ22 | Disease/Pest | Farmer finds vertical tunnels at root zone/offshoots base, soil tunnels on leaf base, and death of newly planted offshoots. |
| Disease/Pest CQ23 | Disease/Pest | Farmer sees silken webbings around fruits/spikelets, leathery fruit skin, and fruits become reddish-brown. |
| Disease/Pest CQ24 | Disease/Pest | Farmer reports light brown spots with dark edges and dark gray spots with reddish-brown edges on leaflet. |
| Disease/Pest CQ25 | Disease/Pest | Farmer sees black sooty rot on leaflet. |
| Control Methods CQ1 | Control Methods | Farmer asks for chemical control of Red palm weevil. |
| Control Methods CQ2 | Control Methods | Farmer asks for chemical control of Black scorch disease. |
| Control Methods CQ3 | Control Methods | Farmer asks for biological control of Palm frond borer damage. |
| Control Methods CQ4 | Control Methods | Farmer asks for biological control of Red palm weevil. |
| Control Methods CQ5 | Control Methods | Farmer asks for chemical control of Inflorescence rot disease. |
| Control Methods CQ6 | Control Methods | Farmer asks for cultural control of Fusarium wilt disease. |
| Control Methods CQ7 | Control Methods | Farmer asks for biological control of Fruit stalk borer damage. |
| Control Methods CQ8 | Control Methods | Farmer asks for chemical control of Bayoud disease. |
| Control Methods CQ9 | Control Methods | Farmer asks for cultural control of Black scorch disease. |
| Control Methods CQ10 | Control Methods | Farmer asks for chemical control of Diplodia leaf-base disease. |
| Control Methods CQ11 | Control Methods | Farmer asks for application rate of Bavistin for Inflorescence rot disease. |
| Control Methods CQ12 | Control Methods | Farmer asks for application rate of Mancozeb for Black scorch disease. |
| Control Methods CQ13 | Control Methods | Farmer asks for application rate and method of Cypermethrin for Red palm weevil. |
| Control Methods CQ14 | Control Methods | Farmer asks how to apply Sodium hypochlorite for Fusarium wilt disease. |
| Control Methods CQ15 | Control Methods | Farmer asks which disease/pest Methyl Bromide is used for. |
| Control Methods CQ16 | Control Methods | Farmer asks what Metalaxyl-M is and for which disease/pest it is used. |
| Control Methods CQ17 | Control Methods | Farmer asks for chemical control of Graphiola leaf spot disease. |
| Control Methods CQ18 | Control Methods | Farmer asks for cultural control of Graphiola leaf spot disease. |
| Control Methods CQ19 | Control Methods | Farmer asks for biological control of Longhorn date palm stem borer damage. |
| Control Methods CQ20 | Control Methods | Farmer asks for application rate and method of Methidathion for Red palm weevil. |
| Symptom CQ1 | Symptom | Researcher asks which symptoms are associated with Fusarium wilt disease. |
| Symptom CQ2 | Symptom | Researcher asks which symptoms are associated with Red palm weevil damage. |
| Symptom CQ3 | Symptom | Researcher asks which symptoms are associated with Inflorescence rot disease. |
| Symptom CQ4 | Symptom | Researcher asks which symptoms are associated with Black scorch disease. |
| Symptom CQ5 | Symptom | Researcher asks which symptoms are associated with Graphiola leaf spot disease. |
| Symptom CQ6 | Symptom | Researcher asks for most common general symptoms of plant disease/pest damage. |
| Symptom CQ7 | Symptom | Student asks the meaning of “Die Back” symptom. |
| Symptom CQ8 | Symptom | Student asks the meaning of “Blight” symptom. |
| Symptom CQ9 | Symptom | Student asks the meaning of “Discolouration” symptom. |
| Symptom CQ10 | Symptom | Student asks the meaning of “Scorch” symptom. |
| Symptom CQ11 | Symptom | Researcher asks distinct characteristics of “Wilting” symptom. |
| Symptom CQ12 | Symptom | Researcher asks distinct characteristics of “Scorch” symptom. |
| Symptom CQ13 | Symptom | Researcher asks distinct characteristics of “Shot_Hole” symptom. |
| Symptom CQ14 | Symptom | Researcher asks distinct characteristics of “Gummosis” symptom. |
| Symptom CQ15 | Symptom | Researcher asks distinct characteristics of “Blight” symptom. |
| Causal Agents CQ1 | Causal Agents | Pathologist asks scientific name of major agents of Inflorescence rot disease. |
| Causal Agents CQ2 | Causal Agents | Pathologist asks scientific name of major agents of Black scorch disease. |
| Causal Agents CQ3 | Causal Agents | Pathologist asks scientific name of major agents of Ganoderma butt rot disease. |
| Causal Agents CQ4 | Causal Agents | Pathologist asks scientific name of major agents of Anthracnose disease of date palm. |
| Causal Agents CQ5 | Causal Agents | Pathologist asks scientific name of major agents of Diplodia leaf-base disease. |
| Causal Agents CQ6 | Causal Agents | Pathologist asks scientific name of major agents of Fusarium wilt disease. |
| Causal Agents CQ7 | Causal Agents | Pathologist asks scientific name of major agents of Reddish brown parallel spot disease. |
| Causal Agents CQ8 | Causal Agents | Pathologist asks scientific name of major agents of Date palm Dubas bug damage. |
| Causal Agents CQ9 | Causal Agents | Pathologist asks scientific name of major agents of Lesser date moth damage. |
| Causal Agents CQ10 | Causal Agents | Pathologist asks scientific name of major agents of Palm frond borer damage. |
| Causal Agents CQ11 | Causal Agents | Pathologist asks scientific name of major agents of Longhorn date palm stem borer damage. |
| Causal Agents CQ12 | Causal Agents | Pathologist asks scientific name of major agents of Mealy bugs damage. |
| Causal Agents CQ13 | Causal Agents | Student asks most common type of biotic factors causing plant disease/damage. |
| Causal Agents CQ14 | Causal Agents | Researcher asks environmental factors contributing to Inflorescence rot disease. |
| Causal Agents CQ15 | Causal Agents | Researcher asks environmental factors contributing to Black scorch disease. |
| Causal Agents CQ16 | Causal Agents | Researcher asks environmental factors contributing to Red palm weevil, Rhynchophorus Ferrugineus. |
| Causal Agents CQ17 | Causal Agents | Researcher asks agricultural practices contributing to Fusarium wilt disease. |
| Causal Agents CQ18 | Causal Agents | Researcher asks agricultural practices contributing to Red palm weevil damage. |
| Causal Agents CQ19 | Causal Agents | Researcher asks transmission mode of Fusarium Oxysporum Schlecht. |
| Causal Agents CQ20 | Causal Agents | Researcher asks transmission mode of Rhynchophorus Ferrugineus. |
| Others CQ1 | Others | Farmer asks active time or outbreak time of Rhynchophorus Ferrugineus. |
| Others CQ2 | Others | Farmer asks expected outbreak time of Inflorescence rot disease. |
| Others CQ3 | Others | Farmer asks which date palm varieties are susceptible to Black scorch disease. |
| Others CQ4 | Others | Farmer asks which varieties are susceptible to Fusarium wilt disease. |
| Others CQ5 | Others | Farmer asks which varieties are susceptible to Inflorescence rot disease. |
| Others CQ6 | Others | Farmer asks which varieties are susceptible to Graphiola leaf spot disease. |
| Others CQ7 | Others | Researcher asks possible affected plant parts by Graphiola leaf spot disease. |
| Others CQ8 | Others | Researcher asks possible affected plant parts by Inflorescence rot disease. |
| Others CQ9 | Others | Researcher asks possible affected plant parts by Red palm weevil damage. |
| Others CQ10 | Others | Researcher asks possible affected plant parts by Longhorn date palm stem borer damage. |
