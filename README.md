<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prontuário Rápido - Protocolos Médicos</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #34495e;
            --accent: #3498db;
            --success: #27ae60;
            --bg: #f4f7f6;
            --text: #333;
        }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; display: flex; height: 100vh; margin: 0; background-color: var(--bg); color: var(--text); overflow: hidden; }
        .sidebar { width: 280px; background: var(--primary); color: white; padding: 20px 15px; overflow-y: auto; display: flex; flex-direction: column; gap: 8px; }
        .sidebar h2 { font-size: 1.2rem; margin-bottom: 10px; text-align: center; border-bottom: 1px solid var(--secondary); padding-bottom: 10px; }
        .category-title { font-size: 0.85rem; color: #bdc3c7; text-transform: uppercase; margin-top: 15px; margin-bottom: 5px; letter-spacing: 1px; }
        .nav-btn { display: block; width: 100%; text-align: left; background: var(--secondary); color: white; border: none; padding: 10px 15px; cursor: pointer; border-radius: 6px; font-size: 13px; transition: background 0.2s; }
        .nav-btn:hover { background: var(--accent); }
        .nav-btn.active { background: var(--accent); font-weight: bold; }
        .copyright { margin-top: auto; padding-top: 20px; font-size: 11px; text-align: center; color: #7f8c8d; border-top: 1px solid var(--secondary); }
        .content { flex: 1; padding: 30px; overflow-y: auto; }
        .section { display: none; animation: fadeIn 0.3s ease-in-out; }
        .section.active { display: block; }
        .section-title { margin-top: 0; color: var(--primary); border-bottom: 2px solid var(--accent); padding-bottom: 10px; margin-bottom: 20px; }
        .item { background: white; padding: 20px; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.05); margin-bottom: 20px; position: relative; }
        .item h3 { margin-top: 0; font-size: 16px; color: var(--secondary); margin-bottom: 15px; padding-right: 80px; }
        .item pre { white-space: pre-wrap; font-family: 'Consolas', 'Monaco', monospace; font-size: 13px; line-height: 1.5; color: #444; background: #f8f9fa; padding: 15px; border-left: 4px solid var(--accent); border-radius: 0 4px 4px 0; margin: 0; overflow-x: auto; }
        .copy-btn { position: absolute; top: 20px; right: 20px; background: var(--accent); color: white; border: none; padding: 8px 15px; cursor: pointer; border-radius: 4px; font-size: 13px; font-weight: bold; transition: background 0.2s; }
        .copy-btn:hover { background: #2980b9; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

    <div class="sidebar">
        <h2>Prontuário Rápido</h2>
        
        <div class="category-title">Emergência & UTI</div>
        <button class="nav-btn active" onclick="showSection('admissao', this)">Admissão & Exames Físicos</button>
        <button class="nav-btn" onclick="showSection('trauma', this)">Trauma & Reanimação</button>
        <button class="nav-btn" onclick="showSection('cardiologia', this)">Cardiologia & Vascular</button>
        <button class="nav-btn" onclick="showSection('dva-sedacao', this)">DVA, Sedação & IOT</button>
        <button class="nav-btn" onclick="showSection('pcr-sepse', this)">PCR, Óbito & Sepse</button>
        <button class="nav-btn" onclick="showSection('procedimentos', this)">Procedimentos Invasivos</button>

        <div class="category-title">Ambulatório</div>
        <button class="nav-btn" onclick="showSection('ivas', this)">IVAS & Respiratório</button>
        <button class="nav-btn" onclick="showSection('infecto', this)">Infectologia & Gastro</button>
        <button class="nav-btn" onclick="showSection('has-dm', this)">HAS, DM & Crônicas</button>
        <button class="nav-btn" onclick="showSection('sintomaticos', this)">Analgesia & Sintomáticos</button>
        <button class="nav-btn" onclick="showSection('oftalmo-oto', this)">Oftalmologia & Otorrino</button>

        <div class="category-title">Pediatria & GO</div>
        <button class="nav-btn" onclick="showSection('pediatria', this)">Pediatria (Urgências)</button>
        <button class="nav-btn" onclick="showSection('macetes-ped', this)">Macetes Pediatria</button>
        <button class="nav-btn" onclick="showSection('gineco', this)">Ginecologia & ISTs</button>
        <button class="nav-btn" onclick="showSection('obstetricia', this)">Obstetrícia (Rotina/Urg)</button>

        <div class="category-title">Complementares</div>
        <button class="nav-btn" onclick="showSection('ortopedia', this)">Ortopedia & Trauma</button>
        <button class="nav-btn" onclick="showSection('hidroeletroliticos', this)">Distúrbios Hidroeletrolíticos</button>
        <button class="nav-btn" onclick="showSection('peconhentos', this)">Peçonhentos & Psiquiatria</button>
        <button class="nav-btn" onclick="showSection('antibioticos', this)">Guia de Antibióticos</button>
        <button class="nav-btn" onclick="showSection('exames-img', this)">Laudos & Exames de Imagem</button>

        <div class="copyright">
            &copy; 2026 Direitos reservados:<br>Fernando Luis Godoy        </div>
    </div>

    <div class="content">

        <!-- ===================== ADMISSÃO ===================== -->
        <div id="admissao" class="section active">
            <h2 class="section-title">Admissão & Exames Físicos</h2>

            <div class="item">
                <h3>Admissão Sala Vermelha</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>### Sala Vermelha ### 
Nome paciente: 
Data de nascimento: 
Data de admissão em UPA: 

# Alergia: nega.
# Comorbidades: nega.
# Medicações de uso contínuo: nega.
# HDA: Paciente vem via fluxo/trazida pelo SAMU para atendimento nesta unidade devido quadro de 

# Objetivo:
- Sinais Vitais: PA 120/85 mmHg | FC: 72 bpm | FR: 20 irpm | SatO2: 98% em ar ambiente 
- Ectoscopia: BEG, normocorad, hidratad, anictéric, acianótic, afebril, pele íntegra.
- Neurológico: LOTE, Glasgow 15, PIFR, sem déficits neurológicos.
- Aparelho Cardiológico: RCR, 2T, BNF, SS.
- Aparelho Respiratório: Eupnéia em ar ambiente, sem esforço respiratório (Saturação de oxigênio 99%), expansibilidade pulmonar preservada, MVUA, sem ruídos adventícios.
- Abdome: Inocente, normotenso, RHA+, indolor à palpação superficial e profunda, sem sinais de peritonismo e/ou visceromegalias. Sinais de Piparote, Blumberg, Murphy e Giordano negativos.
- Extremidades: Aquecidas, perfusão periférica normal TEC < 2 segundos, pulsos amplos e simétricos, sem edemas.

# Resultados de Exames:
- ECG:
- Laboratoriais: Hemograma (Hb, Ht, Leuc, Plaq) | Na | K | Uréia | Creatinina | TGO | TGP | Bilirrubinas (BT, BI, BD) | TP % RNI | TAP seg | Proteina C Reativa | CK | CKMB | Troponina | Gasometria Arterial (pH, pO2, pCO2, HCO3, BE, Sat.O2) | EQU.
- Raio-X de Tórax:

# Conduta:
- Suporte clínico
- Monitorização contínua
- Sinais vitais e cuidados gerais
- Oxigenioterapia conforme necessário
- Prescrevo sintomáticos 
- Solicito exames laboratoriais e urina para avaliação metabólica
- Demais conforme prescrição médica</pre>
            </div>

            <div class="item">
                <h3>Exame Físico Adulto Homem</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>EXAME FÍSICO ADULTO HOMEM
ANTECEDENTES PESSOAIS: NEGA ALERGIA MEDICAMENTOSA. NEGA CARDIOPATIA. NEGA NEFROPATIA. NEGA COMORBIDADES. NEGA MEDICAMENTOS DE USO CONTÍNUO.

ECTOSCOPIA: BOM ESTADO GERAL. LÚCIDO E ORIENTADO EM TEMPO E ESPAÇO COM FALA E LINGUAGEM PRESERVADOS. FÁSCIES ATÍPICA. CORADO, HIDRATADO, ANICTÉRICO, ACIANÓTICO. AFEBRIL. PERFUSÃO MENOR QUE 2 SEGUNDOS. SINAL DE CACIFO NEGATIVO. MARCHA ATÍPICA. PELE ÍNTEGRA COM PILIFICAÇÃO ADEQUADA PARA SEXO E IDADE. 

OROSCOPIA: OROFARINGE SEM HIPEREMIA. AUSÊNCIA DE FOCOS PURULENTOS. AUSÊNCIA DE SINAL DA VELA.
OTOSCOPIA: CANAL AUDITIVO SEM HIPEREMIA. MEMBRANA TIMPÂNICA TRANSPARENTE. AUSÊNCIA DE OTORREIA E OTORRAGIA. SEM SINAIS DE MASTOIDITE.

CARDÍACO: AUSÊNCIA DE CIRCULAÇÃO COLATERAL. AUSÊNCIA DE EDEMA, CIANOSE, ESTASE JUGULAR, ORTOPNEIA OU ASCITE. AUSÊNCIA DE FRÊMITOS PALPÁVEIS. 2 BULHAS RÍTMICAS E NORMOFONÉTICAS SEM SOPROS.

TORÁCICO: TÓRAX NORMAL. AUSÊNCIA DE GÂNGLIOS PALPÁVEIS. EXPANSIBILIDADE PASSIVA E ATIVA PRESERVADAS. NÃO FAZ USO DE MUSCULATURA ACESSÓRIA. MURMÚRIOS VESICULARES FISIOLOGICAMENTE DISTRIBUÍDOS SEM RUÍDOS ADVENTÍCIOS.

ABDOMINAL: ABDOME PLANO. RUÍDOS HIDROAÉREOS PRESENTES E NORMOATIVOS. SOM TIMPÂNICO EXCETO EM HIPOCÔNDRIO DIREITO. ESPAÇO DE TRAUBE LIVRE. SEM SINAIS DE HÉRNIAS, RIGIDEZ ABDOMINAL OU SENSIBILIDADE DOLOROSA. SINAL DE MURPHY NEGATIVO. BLUMBERG NEGATIVO. GIORDANO NEGATIVO.

VASCULAR: SINAL DE HOMANS NEGATIVO. SINAL DE OLOW NEGATIVO. SINAL DE BANCROFT NEGATIVO. SINAL DE BANDEIRA NEGATIVO. SINAL DE MOSES NEGATIVO.

NEUROLÓGICO: GLASGOW 15. PUPILAS ISOCORICAS ISOFOTORREAGENTES. AUSENCIA DE NISTAGMO, ESTRABISMO OU OUTRAS ALTERAÇÕES OCULARES. MOTRICIDADE VOLUNTÁRIA PRESERVADA. FORÇA MUSCULAR GRAU 5. EQUILÍBRIO ESTÁTICO E DINÂMICO PRESERVADOS AVALIADOS ATRAVÉS DA MANOBRA DE ROMBERG. COORDENAÇÃO MOTORA PRESERVADA. REFLEXOS PRESERVADOS (BICIPITAL, TRICIPITAL, ESTILORRADIAL, PATELAR E AQUILEU). SENSIBILIDADE PRESERVADA.</pre>
            </div>

            <div class="item">
                <h3>Exame Físico Adulto Mulher</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>EXAME FÍSICO ADULTO MULHER
ANTECEDENTES PESSOAIS: NEGA ALERGIA MEDICAMENTOSA. NEGA CARDIOPATIA. NEGA NEFROPATIA. NEGA COMORBIDADES. NEGA MEDICAMENTOS DE USO CONTÍNUO.

ECTOSCOPIA: BOM ESTADO GERAL. LÚCIDA E ORIENTADA EM TEMPO E ESPAÇO COM FALA E LINGUAGEM PRESERVADOS. FÁSCIES ATÍPICA. CORADA, HIDRATADA, ANICTÉRICA, ACIANÓTICA. AFEBRIL. PERFUSÃO MENOR QUE 2 SEGUNDOS. SINAL DE CACIFO NEGATIVO. MARCHA ATÍPICA. PELE ÍNTEGRA COM PILIFICAÇÃO ADEQUADA PARA SEXO E IDADE. PELE COM TEXTURA, ELASTICIDADE, MOBILIDADE E TURGOR PRESERVADOS.

OROSCOPIA: OROFARINGE SEM HIPEREMIA. AUSÊNCIA DE FOCOS PURULENTOS. AUSÊNCIA DE SINAL DA VELA
OTOSCOPIA: CANAL AUDITIVO SEM HIPEREMIA. MEMBRANA TIMPÂNICA TRANSPARENTE. AUSÊNCIA DE OTORREIA. AUSÊNCIA DE OTORRAGIA. AUSÊNCIA DE EDEMA AURICULAR. SEM SINAIS DE MASTOIDITE.

CARDÍACO: AUSÊNCIA DE CIRCULAÇÃO COLATERAL. AUSÊNCIA DE EDEMA, CIANOSE, ESTASE JUGULAR, ORTOPNEIA OU ASCITE. AUSÊNCIA DE FRÊMITOS PALPÁVEIS. 2 BULHAS RÍTMICAS E NORMOFONÉTICAS SEM SOPROS.

TORÁCICO: TÓRAX NORMAL. AUSÊNCIA DE GÂNGLIOS PALPÁVEIS. EXPANSIBILIDADE PASSIVA E ATIVA PRESERVADAS. NÃO FAZ USO DE MUSCULATURA ACESSÓRIA. MURMÚRIOS VESICULARES FISIOLOGICAMENTE DISTRIBUÍDOS SEM RUÍDOS ADVENTÍCIOS.

ABDOMINAL: ABDOME PLANO. RUÍDOS HIDROAÉREOS PRESENTES NORMOATIVOS. SOM TIMPÂNICO EXCETO EM HIPOCÔNDRIO DIREITO. ESPAÇO DE TRAUBE LIVRE. SEM SINAIS DE HÉRNIAS, RIGIDEZ ABDOMINAL OU SENSIBILIDADE DOLOROSA. SINAL DE MURPHY NEGATIVO. BLUMBERG NEGATIVO. GIORDANO NEGATIVO.

VASCULAR: SINAL DE HOMANS NEGATIVO. SINAL DE OLOW NEGATIVO. SINAL DE BANCROFT NEGATIVO. SINAL DE BANDEIRA NEGATIVO. SINAL DE MOSES NEGATIVO.

NEUROLÓGICO: GLASGOW 15. PUPILAS ISOCORICAS ISOFOTORREAGENTES. AUSENCIA DE NISTAGMO, ESTRABISMO OU OUTRAS ALTERAÇÕES OCULARES. MOTRICIDADE VOLUNTÁRIA DE MEMBROS PRESERVADA. FORÇA MUSCULAR GRAU 5 EM MEMBROS. EQUILÍBRIO ESTÁTICO E DINÂMICO PRESERVADOS AVALIADOS ATRAVÉS DA MANOBRA DE ROMBERG. COORDENAÇÃO MOTORA PRESERVADA. REFLEXOS PRESERVADOS (BICIPITAL, TRICIPITAL, ESTILORRADIAL, PATELAR E AQUILEU). SENSIBILIDADE PRESERVADA.</pre>
            </div>

            <div class="item">
                <h3>Corpo de Delito</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># CORPO DE DELITO:
PACIENTE ADMITIDO PARA EXAME DE CORPO DE DELITO VIA MÉDICO PLANTONISTA DA UNIDADE DE PRONTO-ATENDIMENTO. NEGA QUEIXAS ÁLGICAS, LESÕES CORPORAIS OU QUAISQUER OUTROS SINTOMAS. 

AO EXAME FÍSICO:
- ECTOSCOPIA: BOM ESTADO GERAL. FÁSCIES ATÍPICA. NORMOCORADO, HIDRATADO, ANICTÉRICO, ACIANÓTICO, AFEBRIL. AUSÊNCIA DE GÂNGLIOS PALPÁVEIS. PELE ÍNTEGRA COM PILIFICAÇÃO ADEQUADA PARA SEXO E IDADE.
- OROSCOPIA: OROFARINGE SEM HIPEREMIA. AUSÊNCIA DE FOCOS PURULENTOS.
- OTOSCOPIA: CANAL AUDITIVO SEM HIPEREMIA. MEMBRANA TIMPÂNICA TRANSPARENTE. AUSÊNCIA DE OTORREIA, OTORRAGIA OU EDEMA AURICULAR.
- NEUROLÓGICO: LÚCIDO E ORIENTADO EM TEMPO E ESPAÇO COM FALA E LINGUAGEM PRESERVADAS, GLASGOW 15, PUPILAS ISOCÓRICAS E ISOFOTORREAGENTES, AUSÊNCIA DE NISTAGMO, ESTRABISMO OU OUTRAS ALTERAÇÕES OCULARES. MOTRICIDADE VOLUNTÁRIA DE MEMBROS PRESERVADA. FORÇA MUSCULAR GRAU 5 EM MEMBROS. EQUILÍBRIO ESTÁTICO E DINÂMICO PRESERVADOS. COORDENAÇÃO MOTORA, REFLEXOS E SENSIBILIDADE PRESERVADOS. MARCHA ATÍPICA. SEM QUAISQUER DÉFICITS NEUROLÓGICOS.
- APARELHO CARDÍACO: RITMO CARDÍACO REGULAR, 2 BULHAS RÍTMICAS E NORMOFONÉTICAS SEM SOPROS. AUSÊNCIA DE CIRCULAÇÃO COLATERAL. AUSÊNCIA DE EDEMA, CIANOSE, ESTASE JUGULAR, ORTOPNEIA OU ASCITE.
- APARELHO RESPIRATÓRIO: TÓRAX NORMAL. EUPNEIA EM AR AMBIENTE, SEM ESFORÇO RESPIRATÓRIO. NÃO FAZ USO DE MUSCULATURA ACESSÓRIA, SATURAÇÃO DE OXIGÊNIO 100%, EXPANSIBILIDADE PASSIVA E ATIVA PRESERVADAS, MURMÚRIOS VESICULARES FISIOLOGICAMENTE DISTRIBUÍDOS, SEM RUÍDOS ADVENTÍCIOS.
- ABDOMINAL: ABDOME PLANO. RUÍDOS HIDROAÉREOS PRESENTES E NORMOATIVOS. SOM TIMPÂNICO EXCETO EM HIPOCÔNDRIO DIREITO. ESPAÇO DE TRAUBE LIVRE. SEM SINAIS DE HÉRNIAS, RIGIDEZ ABDOMINAL OU SENSIBILIDADE DOLOROSA. SEM SINAIS DE PERITONISMO E/OU VISCEROMEGALIAS. SINAL DE MURPHY NEGATIVO. BLUMBERG NEGATIVO. PIPAROTE NEGATIVO. GIORDANO NEGATIVO.
- EXTREMIDADES: AQUECIDAS, PERFUSÃO PERIFÉRICA NORMAL (MENOR QUE 2 SEGUNDOS), PULSOS AMPLOS E SIMÉTRICOS, SEM EDEMAS. SINAL DE CACIFO NEGATIVO.

CONSTATADA A ESTABILIDADE HEMODINÂMICA E AUSÊNCIA DE LESÕES CORPORAIS. SEM NECESSIDADE OU INDICAÇÃO DE PERMANÊNCIA EM UNIDADE. PACIENTE APTO PARA RECLUSÃO OU QUAISQUER OUTRAS CONDUTAS ADOTADAS POR EQUIPE POLICIAL. FICO A DISPOSIÇÃO. SEM MAIS.</pre>
            </div>
        </div>

        <!-- ===================== TRAUMA ===================== -->
        <div id="trauma" class="section">
            <h2 class="section-title">Trauma & Reanimação</h2>

            <div class="item">
                <h3>ABCDE do Trauma</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>ABCDE DO TRAUMA
PACIENTE VÍTIMA DE ACIDENTE AUTOMOBILÍSTICO ENTRE CARRO X MOTO COMPARECE EM UNIDADE DE PRONTO ATENDIMENTO TRAZIDO PELOS BOMBEIROS EM PRANCHA RÍGIDA E COLA CERVICAL.

A: VIAS AÉREAS PÉRVIAS, FONAÇÃO PRESERVADA. POSICIONADO EM PRANCHA RÍGIDA + COLA CERVICAL SEM QUEIXAS ÁLGICAS. RETIRADOS SEM INTERCORRÊNCIAS. 
B: MVFD SEM RUÍDOS ADVENTÍCIOS, TÓRAX SIMÉTRICO, EXPANSIBILIDADE PRESERVADA, SEM SINAIS DE DESCONFORTO RESPIRATÓRIO, EUPNEICO EM AR AMBIENTE. 
C: BRNF S/ SOPROS, JUGULARES NORMODISTENDIDAS, PULSOS CHEIOS E SIMÉTRICOS. ABDOME FLÁCIDO, INDOLOR A PALPAÇÃO, SEM SINAIS DE IRRITAÇÃO PERITONEAL. PELVE ESTÁVEL. 
D: PUPILAS ISOFOTORREAGENTES. GLASGOW 15. CONSCIENTE E ORIENTADO, SEM DÉFICITS MOTORES. 
E: SEM DOR A PALPAÇÃO DE COLUNA CERVICAL, TORÁCICA, LOMBAR E SEM EVIDÊNCIAS DE FRATURA. SEM FCC.

ÍNDICE DE CHOQUE: FC/PAS. SE MAIOR OU IGUAL A 0,9 CONSIDERAR TRANSFUSÃO SANGUÍNEA.</pre>
            </div>

            <div class="item">
                <h3>Trauma Torácico</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>PNEUMOTÓRAX ABERTO: ORIFÍCIO COM TÓRAX ACOMETIDO SEM MOVIMENTO. CURATIVO DE 3 PONTOS. DEPOIS DRENAR.
PNEUMOTÓRAX HIPERTENSIVO: TÓRAX EXPANDIDO NO HEMITÓRAX ACOMETIDO. HIPERTIMPANICO. PUNCIONAR COM ABOCATH 14 NO QUINTO ESPAÇO INTERCOSTAL LINHA AXILAR MÉDIA. TIRAR AGULHA E DEIXAR ABOCATH.
HEMOTÓRAX: RESCUCITAÇÃO VOLEMICA, HEMODERIVADO COM CONCENTRADO DE HEMACIA O – E DEPOIS DRENAR O TÓRAX.
CONTUSÃO PULMONAR: 
TÓRAX INSTÁVEL: FX EM 3 OU MAIS ARCOS COSTAIS EM DOIS OU MAIS LOCAIS. ANALGESIA INTENSA. INTUBAR.</pre>
            </div>

            <div class="item">
                <h3>Hemoderivados e Transfusão</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>CONCENTRADO DE HEMÁCIAS (250 A 300ML/UN): CADA UNIDADE ELEVA O HB EM 1 A 1,5 E O HT EM 3%
PLASMA FRESCO CONGELADO (180 A 200ML/UNIDADE): SEMPRE QUE O RNI > 1,5
CONCENTRADO DE PLAQUETAS (50ML/UNIDADE): EM PLAQUETAS < 50.000 OU 100.000 COM SANGRAMENTO ATIVO. CADA UNIDADE AUMENTA DE 5.000 A 10.000 PLAQUETAS. POOL: +/- 250ML. AFERESE: +/- 350ML
CRIOPRECIPITADO (10 A 20 ML CADA UNIDADE RANDÔMICA): GERALMENTE USA-SE DE 7 A 10 UNIDADES RANDÔMICAS. USADO SE FIBRINOGÊNIO ESTIVER MENOR DE 200 MG/DL. CADA UNIDADE AUMENTA O FIBRINOGENIO EM 10 MG/DL

CRITÉRIOS DE TRANSFUSÃO:
HB > 8 | HT > 21% | PLAQUETAS > 50.000 | PROTROMBINA < 1,5 | FIBRINOGÊNIO > 200</pre>
            </div>
        </div>

        <!-- ===================== CARDIOLOGIA ===================== -->
        <div id="cardiologia" class="section">
            <h2 class="section-title">Cardiologia & Vascular</h2>

            <div class="item">
                <h3>Protocolo Dor Torácica Inicial</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># PROTOCOLO DOR TORÁCICA
AAS 100 MG – 3 COMPRIMIDOS MASTIGAR E ENGOLIR AGORA. 
CLOPIDOGREL 50 MG – 4 COMPRIMIDOS TOMAR AGORA.
SINVASTATINA 20 MG – 2 COMPRIMIDOS TOMAR AGORA.
ATENOLOL 50 MG – 1 COMPRIMIDO TOMAR AGORA. (CONTRA-INDICAÇÃO: FR < 60 BPM ; PAS < 100 MMHG ; DISFUNÇÃO DE VE GRAVE ; HIPOPERFUSÃO PERIFÉRICA ; INTERVALO PR > 0,24 SEGUNDOS ; BAV DE 2º OU 3º GRAU ; DPOC OU ASMA GRAVE).
ENALAPRIL 10 MG – 1 COMPRIMIDO TOMAR AGORA. (CONTRA-INDICAÇÃO: PAS < 100 MMHG ; HIPOPERFUSÃO PERIFÉRICA ; SINAIS DE CHOQUE CARDIOGÊNICO).
MORFINA 10 MG/ML – 1 AMPOLA APLICAR EV 1 AMPOLA SE PERSISTIR DOR.

- MONITORIZAÇÃO CARDÍACA CONTÍNUA
- ECG – AGORA POR FAVOR (IAM COM OU SEM SUPRA ST – EM 10/10 MINUTOS)
- SOLICITO ENZIMAS CARDÍACAS (CPK, CKMB, TROPONINA)
- REALIZAR ACESSO VENOSO – PREFERENCIALMENTE EM MEMBRO SUPERIOR ESQUERDO (MSE), CALIBRE N°20, SE POSSÍVEL
- ADMINISTRAR MEDICAÇÕES CONFORME PRESCRIÇÃO MÉDICA
- MANTER EM OBSERVAÇÃO CONTÍNUA</pre>
            </div>

            <div class="item">
                <h3>IAM Com Supra ST (Conduta + Trombólise)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>IAM COM SUPRA:
1. DIETA ZERO E RESTRIÇÃO EM LEITO
2. MONITORIZAÇÃO MULTIPARAMÉTRICA
3. AAS 100MG 24/24H (INICIAR 24H APÓS ATAQUE)
4. CLOPIDOGREL 75MG V.O 24/24H
5. CAPTOPRIL 25MG V.O 24/24H CEDO
6. SINVASTATINA 40MG V.O A NOITE

##### TROMBÓLISE - SEGUIR ESTRITAMENTE #####
-- 1º BOLUS INICIAL - 30MG ENOXAPARINA EV EM BOLUS + 15MG ALTEPLASE EV EM BOLUS
-- 2º ENOXAPARINA 70MG SC
-- 3º ALTEPLASE 50MG EV EM 30 MIN (BIC)
-- 4º ALTEPLASE 35MG EV EM 60 MIN (BIC)

7. ENOXAPARINA 70MG SC 12/12H (REALIZAR 1ª DOSE DURANTE TROMBÓLISE - 2º ITEM)
8. ECG - REALIZAR AO TÉRMINO DE TROMBÓLISE OU SE INTERCORRÊNCIA
9. CORREÇÃO DE HGT CONFORME PROTOCOLO NÃO NEFROPATA - SUSPENDER HIPOGLICEMIANTES ORAIS
10. CURVA TROPONINA - COLETA EM 0 - 6 - 12H
11. NAUSEDRON 1AMP EV 8/8H SE NÁUSEA OU VÔMITO
12. DIPIRONA 1 AMP EV 6/6H SE FEBRE
13. MORFINA 1AMP + 9ML AD - REALIZAR 2ML EV EM BOLUS >=ACM <<
14. SSVV + CCGG + HGT 3/3H
15. O2 SUPLEMENTAR SE SAT < 90% (UTILIZAR MNR SE > 4L)
16. NOTIFICAR PLANTONISTA SE INTERCORRÊNCIAS</pre>
            </div>

            <div class="item">
                <h3>IAM Sem Supra ST (IAMSST / Angina Instável)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>NÃO REALIZA FIBRINOLÍTICO NESSES CASOS! PODE SURGIR IAM COM SUPRA. NÃO LIBERAR APÓS ESTABILIZAR.

1º: TIRAR A DOR DO PACIENTE! NITRATO (ISORDIL 5MG SUBLINGUAL PODE REPETIR ATÉ 3 VEZES COM INTERVALO DE 10 MINUTOS ENTRE ELAS). SE NÃO MELHORAR, PROPANOLOL 20 MG OU ATENOLOL 25 MG. ESPERA MAIS 20 MIN. MORFINA 2MG EV SE NÃO MELHORAR.
- TRIDIL 5 A 10 ML/H. NÃO FAZER NITRATO EM HIPOTENSOS

2º: AAS 100MG 3 CPS MASTIGADOS + CLOPIDOGREL 75MG 4 CPS VO (SE FOR TRANSFERIDO EM MAIS DE 24H APENAS. SE TIVER MAIS DE 75 ANOS, APENAS 1CP) + ENOXAPARINA 1MG/KG SUBCUTANEO DE 12/12H (SE FOR TRANSFERIDO EM ATÉ 2H, NÃO PRECISA FAZER).

3º: MANUTENÇÃO: AAS 100MG AO DIA + CLOPIDOGREL 75MG AO DIA + CAPTOPRIL 25MG 12/12H + SINVASTATINA 40MG AO DIA + PROPANOLOL 12/12H + ENOXAPARINA 12/12H.

SE TROPONINA NORMAL OU NÃO TIVER TROPONINA? PENSAR EM DIAGNOSTICOS DIFERENCIAIS E EXCLUIR. REALIZAR SCORE DE HEART (PREVISÃO DE EVENTO CARDIOLOGICO NAS PRÓXIMAS 6 SEMANAS)
HISTÓRIA CLÍNICA: TÍPICA (2), EQUIVALENTE ANGINOSO (1), ATÍPICA (0) 
ECG: INFRA DE ST (2), ALTERAÇÃO DE REPOLARIZAÇÃO (1), NORMAL (0) 
AGE: MAIOR DE 65 (2), ENTRE 45 E 64 (1), MENOS DE 45 (0) 
RISCO: MAIS DE 3 (2), 1 A 3 (1), NENHUM (0)
TROPONINA: TRES VEZES (2), UMA A TRES VEZES (1), NORMAL (0) 

INVESTIGAR E ENCAMINHAR SE: MAIOR OU IGUAL 4 PONTOS.</pre>
            </div>

            <div class="item">
                <h3>Edema Agudo de Pulmão (EAP)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>EDEMA AGUDO PULMÃO:
1. JEJUM E ACESSO CALIBROSO SALINIZADO EV
2. CABECEIRA ELEVADA 80º CONTÍNUO
3. DEXAMETASONA 1 AMP EV EM BOLUS A CADA 24H
4. FUROSEMIDA 40 MG EV 6/6H + AGORA 4 AMP EV EM BOLUS
5. MORFINA 10 MG + AD 8 ML EV ACM OU SE DOR PRECORDIAL
6. AAS 100 MG VO 1 CP APÓS ALMOÇO
7. ESPIRONOLACTONA 25MG 1 COMP VO PELA MANHA
8. SALBUTAMOL 100 MCG INALAR 8 JATOS A CADA 20 MINUTOS POR 3 CICLOS E MANTER 6 PUFFS A CADA 4 HORAS
9. SVD E MONITORIZAÇÃO CONTÍNUA DE DIURESE
10. SUPLEMENTAÇÃO DE O2 ACM - MANTER SAT ENTRE 90-95%

SE O PACIENTE ESTIVER HIPOTENSO: ICC DESCOMPENSADA. PERFIL C. INICIAR DOBUTAMINA (SE SISTOLICA MAIOR DE 90). SE NÃO PUDER, INICIA NORADRENALINA PARA ELEVAR ACIMA DE 90, ASSIM INICIA DOBUTAMINA. VAI DESMAMANDO NORA. TIROU NORA. ENTRO COM VASODILATADOR E DIURETICO. NESSE MEIO TERMO SE USA VNI (SE CONSCIENTE E ORIENTADO).</pre>
            </div>

            <div class="item">
                <h3>Insuficiência Cardíaca Congestiva (ICC)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>IC DIREITA (SISTÊMICA): EDEMA DE MMII, ESTASE JUGULAR, ESPLENOMEGALIA, ASCITE, CREPITAÇÕES.
IC ESQUERDA (PULMONAR): DISPNEIA, TOSSE, ORTOPNEIA, EDEMA AGUDO DE PULMÃO. 

PERFIL CLÍNICO-HEMODINÂMICO:
A: QUENTE E SECO (FUROSEMIDA, HIDROCLOROTIAZIDA, DIGOXINA): está compensado. Ambulatorial. 
B: QUENTE E ÚMIDO (FUROSEMIDA 1MG/KG, REPETIR DE 2 A 3 VEZES + TRIDIL/NIPRIDE + PROFILAXIA TEP E TVP).
C: FRIO E ÚMIDO (1MG/KG DE FUROSEMIDA EV EM BOLUS + PROFILAXIA TEP/TVP. SE NÃO MELHORAR, ASSOCIAR DOBUTAMINA).
No paciente frio e úmido:
1) PA sistólica < 70mmHg: nora + dobuta;
2) PA sistólica 70-90mmHg: dobutamina;
3) PA sistólica > 90mmHg: vasodilatadores venosos.
L: FRIO E SECO (AVALIAR E TRATAR ISQUEMIA + PROFILAXIA TEP). VOLUME SF0.9% 250ML ACM SE EXAGEROU NO DIURETICO.</pre>
            </div>

            <div class="item">
                <h3>AVC (Acidente Vascular Encefálico)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>SUSPEITAR EM: QUADRO NEUROLOGICO SUBITO (DEFICIT FOCAL –PERDA DE FORÇA-, DESVIO DE RIMA, DISARTRIA, CEFALEIA, REBAIXAMENTO DE NÍVEL DE CONSCIENCIA, VERTIGEM).
ESCALA DE CINCINNATI: DESVIO DE RIMA, FALA E QUEDA DO BRAÇO.

DX DIFERENCIAL: HIPOGLICEMIA, PARALISIA DE BELL, AIT, TUMOR CEREBRAL, INTOXICAÇÕES, TROMBOSE VENOSA CEREBRAL.

MONITOR, OXIMETRIA, GLICEMIA CAPILAR, ECG. DIETA ZERO + CABECEIRA ELEVADA
SF0.9% 500ML DE 8/8H PARA MANTER ACESSO SÓ. HEMOGRAMA + SODIO, POTASSIO, UREIA, CREAT, TAP. IOT SE NÃO CONSEGUIR PROTEGER VIA AEREA.
MANTER GLICEMIA ENTRE 140 E 180. DE 2/2H
MANTER TEMPERATURA MENOR DE 37 GRAUS
PRESSAO ABBAIXO DE 220X120MMHG (ISQUEMICO). PRESSAO ENTRE 140-160 SE HEMORRAGICO.
TC MAIS RAPIDO POSSIVEL. ENQUANTO NÃO TEM ELA, APENAS MANTER PRESSAO.
- TROMBOLISE EM ATÉ 4,5 HORAS
- TROMBECTOMIA EM ATÉ 6 HORAS
- CRANIECTOMIA EM ATÉ 48 HORAS
- REABILITAÇÃO PRECOCE
- PREVENÇÃO DE NOVOS EPISÓDIOS. ENCAMINHAR SEMPRE!</pre>
            </div>

            <div class="item">
                <h3>TEP e TVP</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>TROMBOSE VENOSA PROFUNDA (TVP):
A CLÍNICA NÃO É SOBERANA NESSE CASO, PRECISA DO DOPPLER! REALIZAR ESCORE DE WELLS PARA TEP. SE BAIXA PROBABILIDADE, FAZER D-DÍMERO. SE NÃO HOUVER DOPPLER NA UNIDADE, FAZER ENOXAPARINA 1MG/KG SUBCUTANEO E ENCAMINHAR. ALEM DE ANTIINFLAMATÓRIOS E ANALGÉSICOS.

TROMBOEMBOLISMO PULMONAR (TEP):
DISPNEIA, DOR PLEURÍTICA, TOSSE, HEMOPTISE, TAQUIPNEIA, TAQUICARDIA, SINAIS DE TVP, DERRAME PLEURAL, FEBRE.
RX: SINAL DE WESTERMARK, CORCOVA DE HAMPTON, SINAL DE PALLA.
DX PADRÃO OURO: ARTERIOGRAFIA PULMONAR.
SUSPEITA DE TEP COM CHOQUE OU HIPOTENSÃO: ANGIOTC DE TÓRAX IMEDIATAMENTE!
SUSPEITA DE TEP SEM CHOQUE OU HIPOTENSÃO: ESCORE DE WELLS. SE BAIXA OU INTERMEDIÁRIA, D-DÍMERO. SE POSITIVO, ANGIO TC.
- MANTER INR ENTRE 2 E 3 POR AO MENOS 3 MESES. TROMBÓLISE PODE INICIAR EM ATÉ 14 DIAS APÓS INICIO DOS SINTOMAS.
HEPARINA NÃO-FRACIONADA: DOSE DE ATAQUE EV DE 80U/KG + MANUTENÇÃO.
ENOXAPARINA 2MG</pre>
            </div>

            <div class="item">
                <h3>Fibrilação Atrial, Bradiarritmia e Dissecção de Aorta</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>FIBRILAÇÃO ATRIAL:
INSTAVEL: CARDIOVERSAO. APÓS DE MIDAZOLAM 5MG EV BOLUS + MORFINA 2ML EV
ESTAVEL: CHADSVASC. BETABLOQUEADOR. METOPROLOL 5MG VENOSO. PODENDO REPETIR 2X. SE PACIENTE DE ALTO RISCO E COM INICIO DE MAIS DE 24H, PRECISA FAZER ANTICOAGULANTE POR 4 SEMANAS. ENCAMINHAR!!!

BRADIARRITIMIA E INSTABILIDADE:
ATROPINA 1 AMPOLA 1MG EV EM BOLUS DE 5 EM 5 MINUTOS (MÁXIMO DE 3MG).
ADRENALINA 1MG (1 AMPOLA) + 100ML SG5% EV EM BIC: 12ML/H OU 12 MICROGOTAS/MIN. PREPARANDO MARCAPASSO TRANSCUTANEO. SEDAR E ANALGESIA: MIDAZOLAM 2MG EV LENTO + MORFINA 2MG EV.

DISSECÇÃO AGUDA AÓRTICA:
ALVO FC MENOR 60 E PAS MENOR 120MMHG.
ESMOLOL 10MG/ML 3ML EV EM 1 MIN. APÓS: ESMOLOL 250MG/ML 10ML + SG5% 240ML FAZER EM BIC 18ML/H OU METOPROLOL 5MG EV BOLUS MAXIMO 15MG.
NITROPRUSSIATO DE SODIO 1 AMPOLA + SG5% 250ML EM BIC 3ML/H (SE NÃO ATINGIR ALVO DE PA).
MORFINA 10MG/ML + AD 9ML: 3ML EV 5/5MIN ACM.</pre>
            </div>
        </div>

        <!-- ===================== DVA / SEDAÇÃO / IOT ===================== -->
        <div id="dva-sedacao" class="section">
            <h2 class="section-title">DVA, Sedação & IOT</h2>

            <div class="item">
                <h3>Intubação Orotraqueal (IOT)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># INTUBAÇÃO OROTRAQUEAL:
1. PREPARAÇÃO E PARAMENTAÇÃO DA EQUIPE FORMADA POR MÉDICO, ENFERMEIRO E TÉCNICOS DE ENFERMAGEM.
2. PRÉ-OXIGENAÇÃO COM BOLSA VÁLVULA MÁSCARA COM FILTRO.
3. PRÉ-TRATAMENTO COM FENTANIL.
4. PARALISIA COM SUCCINILCOLINA E INDUÇÃO COM ETOMIDATO/MIDAZOLAM.
5. POSICIONAMENTO DO PACIENTE COM COXIM SUBOCCIPITAL.
6. PASSAGEM DE TUBO OROTRAQUEAL NÚMERO 7,5.
7. CONEXÃO AO CIRCUITO FECHADO.
8. CONFIRMAÇÃO POR AUSCULTA DE POSICIONAMENTO CORRETO DE TOT.
9. FIXAÇÃO DE TOT.

# INDUÇÃO SEQUÊNCIA RÁPIDA:
1. FENTANIL 50MG/ML: FAZER 3ML EV LENTO EM 60S.
2. ETOMIDATO 20MG/ML: (0,3MG/KG) 1 AMPOLA EV LENTO.
3. SUCCINILCOLINA 100MG + 10ML DE ÁGUA DESTILADA: FAZER OS 10ML EV EM BOLUS.

# MANUTENÇÃO:
1. FENTANIL/MIDAZOLAM/PROPOFOL
2. BNM ROCURÔNIO/ATRACÚRIO</pre>
            </div>

            <div class="item">
                <h3>Diluição de Sedação e Analgesia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># FENTANIL (infusão 0,7 – 1,0 mcg/kg/h)
Solução I: SF 0,9% 80 ml + Fentanil 20 ml (50 mcg/ml) = solução 10 mcg/ml
Solução II: SF 0,9% 100 ml + Fentanil 40 ml (50 mcg/ml) = solução 40 mcg/ml

# MIDAZOLAM (inicia 0,05 mcg/kg/h e titula entre 0,02 – 0,1 mg/kg/h)
Solução I: SF 0,9% 80 ml + Midazolam 20 ml (5 mg/ml) = solução 1 mg/ml
Solução II: SF 0,9% 100 ml + Midazolam 40 ml (5 mg/ml) = solução 4 mg/ml
Solução III: SF 0,9% 100ML + MIDAZOLAM 6 AMP DE 15MG

# PROPOFOL (5 – 50 mcg/kg/min)
Frasco 20ml 1% = solução 10mg/ml (=10.000 mcg/ml)

# DEXMEDETOMIDINA (Precedex - infunde 1.0 mcg/kg por 10 min e reduz para 0.2 – 0.7 mcg/kg/h)
Solução I: SF 0,9% 48ml + Dexmedetomidina 2 ml (100 mcg/ml) = solução 4 mcg/ml
Solução Dobrada: SF 0,9% 96ml + Dexmedetomidina 4 ml (200 mcg/ml) = solução 4 mcg/ml

# CETAMINA (infusão 0,05 - 0,4 mg/kg/h)
Solução: SF 0,9% 90ml + Ketamina 10ml (50mg/ml) = solução 5mg/ml</pre>
            </div>

            <div class="item">
                <h3>Bloqueadores Neuromusculares (BNM)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>*SUCCINILCOLINA (NÃO INDICADO PARA MANUTENÇÃO, SOMENTE INDUÇÃO)
*ATRACÚRIO (INFUSÃO 0,65 A 0,78MG/KG/MIN)
Solução I: SF 0,9% 30 ML + ATRACÚRIO 20 ml/2,5 ml (10 mg/ml)= solução 4mg/ml
Solução II: SF 0,9% 80ml + Atracúrio 20 ml/2,5ml (10 mg/ml)= solução 2mg/ml

*Cisatracúrio (infusão 0,03 a 0,6 mg/kg/h)
Solução I: SF 0.9% 100 ML + Cisatracúrio 10 ml (2 mg/ml)= solução 0.18 mg/ml

TABELA DE BNM:
- Succinilcolina: Indução 1,0 mg/kg | Ação < 1min / até 10 min | Atenção: taquiFC, aumento PIC/PIO, hiperK, anafilaxia, hipertermia maligna
- Atracúrio: Indução 0,5 | Manutenção 0,65 - 0,78 mg/kg/h | Ação 2-3 min / 20-30 min | Sem efeito cardiovascular, libera histamina
- Cisatracúrio: Indução 0,1 | Manutenção 0,03 - 0,6 mg/kg/h | Ação 2-3 min / 30-40 min | 4x mais potente que atracúrio, não libera histamina
- Pancurônio: Indução 0,1 | Ação 3-5 min / 40-60 min | Simpatomimético, não libera histamina, cuidar disfunção rins/figado
- Rocurônio: Indução 0,6 | Ação 1-2 min / 30-40 min | Efeito cardiovascular mínimo, não libera histamina, mais anafilaxias</pre>
            </div>

            <div class="item">
                <h3>Diluição Drogas Vasoativas</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># NOREPINEFRINA
Solução I: Norepinefrina 1 amp (4 ml) + SG 5% 246 ml = solução 16 mcg/ml.
Solução II: Norepinefrina 5 ampolas (20 ml) + SG 5% 230 ml = solução 80 mcg/ml.

# NITROGLICERINA (TRIDIL)
Diluição: Nitroglicerina 50 mg (10 ml) + SG 5% 240 ml = solução 200 mcg/ml.
Velocidade de infusão: 5 – 60 ml/h.

# NITROPRUSSIATO DE SÓDIO (NIPRIDE)
Diluição: Nitroprussiato de sódio 1 amp (2 ml) + SG 5% 248 ml = solução 200 mcg/ml.
Solução II: Nitroprussiato de sódio 2 amp (4 ml) + SG 5% 246 ml = solução 400 mcg/ml.
(Utilizar equipo apropriado para medicações fotossensíveis).

# DOBUTAMINA
Solução I: Dobutamina 1 ampola (20 ml) + SG 5% 230 ml = solução 1 mg/ml.
Solução II: Dobutamina 2 ampolas (40 ml) + SG 5% 60 ml = solução 5 mg/ml.

# DOPAMINA
Diluição: Dopamina 5 ampolas (50 ml) + SG 5% 200 ml = solução 1 mg/ml.

# EPINEFRINA
Diluição: Epinefrina 1 ampola (1ml) + SF 0,9% 250ml = solução 4 mcg/ml.
Velocidade de infusão: 30 a 150 ml/h.

# AMIODARONA
Dose de ataque (máximo de 5 mg/kg): amiodarona 300 mg + SF 0,9% 100ml. Infundir em 30 minutos.
Dose de manutenção: amiodarona 600 a 900 mg + SG 5% 250ml. Infundir em 24 horas (11 ml/h).

# VASOPRESSINA
Diluição: Vasopressina 2 ampola (2 ml) + SF 0,9% 98 ml = solução 0,4 U/ml.
Velocidade de infusão: 1,5 a 6 ml/h.</pre>
            </div>
        </div>

        <!-- ===================== PCR / ÓBITO / SEPSE ===================== -->
        <div id="pcr-sepse" class="section">
            <h2 class="section-title">PCR, Óbito & Sepse</h2>

            <div class="item">
                <h3>Parada Cardiorrespiratória (PCR)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>PARADA CARDIORRESPIRATÓRIA (PCR)
- CHAMAR O PACIENTE. SE IRRESPONSIVO, CHAMAR EQUIPE
- CHECAR PULSO CAROTÍDEO
- INICIAR COMPRESSAO TORÁCICA IMEDIATAMENTE. LIGAR DESFIBRILADOR E COLOCAR NO MODO PÁ
- 30 COMPRESSÕES PARA 2 VENTILAÇÕES COM BOLSA VÁLVULA-MÁSCARA
- QUANDO O DESFIBRILADOR ESTIVER PRONTO, CHECAR O RITMO

FV E TV SEM PULSO: CHOCAR
SE FOR CHOCÁVEL: DESCONECTAR O AMBU DO TUBO, DESCONECTAR ELETRODO, PASSAR GEL NAS PÃOS, AFASTA!!!!! E CHOQUE IMEDIATO COM CARGA MÁXIMA
VOLTAR IMEDIATAMENTE RCP 30X2
PEGAR ACESSO VENOSO
PROCEDER IOT. MANTER 1 VENTILAÇÃO A CADA 6S QUANDO INTUBA.
PASSARAM 2 MINUTOS, CHECAR NOVAMENTE RITMO. CHOQUE
VOLTAR RCP
ADRENALINA 1 AMPOLA EM BOLUS EV, COM FLUSHING DE 20ML E ELEVA MEMBRO
2 MINUTOS RCP, CHECA RITMO. CHOQUE
AMIODARONA 150MG 2 AMPOLAS EM BOLUS SEGUIDA DE FLUSHING
2 MINUTOS RCP, CHECA RITMO. CHOQUE
ADRENALINA 1 AMPOLA
2 MINUTOS RCP, CHECA RITMO. CHOQUE
AMIODARONA 150MG 1 AMPOLA (ÑÃO REPETIR MAIS, CONTINUAR COM ADRENALINA VEZ SIM VEZ NÃO)
SE VOLTAR, CHECAR PULSO EM JUGULAR.</pre>
            </div>

            <div class="item">
                <h3>Declaração de Óbito</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DECLARAÇÃO DE ÓBITO: 
PACIENTE, ESTADO GRAVÍSSIMO, EM FRANCO CHOQUE SÉPTICO E EM USO DE ALTAS DOSES DE DVA, SOFRE PARADA CARDIORRESPIRATÓRIA EM RITMO ASSISTOLIA. IMEDIATAMENTE, INICIAMOS REANIMAÇÃO CARDIORRESPIRATÓRIA COM RESPECTIVAS MEDICAÇÕES SEGUNDO PROTOCOLO ACLS/AHA, TODAVIA, DURANTE TODO PROCEDIMENTO, PACIENTE NÃO ESBOÇOU NENHUM SINAL DE RETORNO DA CIRCULAÇÃO ESPONTÂNEA. ÀS [HORA ÓBITO], OPTAMOS POR SUSPENDER OS ESFORÇOS. REALIZADO PROTOCOLO DE LINHA RETA, OU SEJA, CHECADO CABOS, GANHOS E DERIVAÇÕES. CONSTATADA AUSÊNCIA DE REFLEXOS DE TRONCO ENCEFÁLICO. ATESTO O ÓBITO E COMUNICO A FAMÍLIA.</pre>
            </div>

            <div class="item">
                <h3>Sepse e Abdome Agudo</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>ABDOME AGUDO / SEPSE:
1. DIETA ZERO ATÉ SEGUNDA ORDEM
2. ACESSO CALIBROSO SALINIZADO (2 ACESSOS SE CHOQUE)
3. RINGER LACTATO 500ML EV AGORA / EXPANSÃO VOLÊMICA DE 30ML/KG EM ATÉ 3 HORAS
4. CEFTRIAXONA 2G + SF 0,9% 100ML EV (DOSE DE ATAQUE)
5. METRONIDAZOL 500 MG EV 08/08H
6. TRAMAL 50 MG + SF 0,9% 100 ML EV 12/12H SE DOR INTENSA
7. ONDANSETRANA 1 AMPOLA EV 08/08H SE NÁUSEAS
8. SONDA NASOGASTRICA CALIBROSA ABERTA
9. SVD E CONTROLE RIGOROSO DE DIURESE
10. BROMOPRIDA 10MG + AD 10ML EV LENTO
11. OMEPRAZOL 40MG EV AGORA
12. DIPIRONA 1G + AD 20ML EV LENTO
13. MORFINA 10MG + 9ML DE AD: FAZER 3ML EV ACM

EXAMES: HMG, NA, K, UREIA, CREAT, LACTATO, TGO, TGP, FA, GGT, AMILASE, TAP, ALBUMINA, HEMOCULTURA 2 AMOSTRAS, EAS, UROCULTURA. RX ABDOME AGUDO. USG ABDME/TC.

ATB NA PRIMEIRA HORA, DE PREFERÊNCIA IMEDIATAMENTE. HIPOVOLEMIA PODE LEVAR A LESÃO RENAL AGUDA PRÉ-RENAL POR PERDER LIQUIDO PELO TERCEIRO ESPAÇO.
EXPANSÃO VOLÊMICA: 30ML/KG EM ATÉ 3 HORAS
- NÃO REALIZAR FUROSEMIDA!!
SVD. DROGAS VASOATIVAS SE IRRESPONSIVO A VOLUME (PAM<75)</pre>
            </div>
        </div>

        <!-- ===================== PROCEDIMENTOS ===================== -->
        <div id="procedimentos" class="section">
            <h2 class="section-title">Procedimentos Invasivos</h2>

            <div class="item">
                <h3>Punção de Acesso Venoso Central</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># REALIZADA PUNÇÃO DE ACESSO VENOSO CENTRAL:

1. Realizadas assepsia e antissepsia da região com clorexidina alcoólica e colocação de campos estéreis.
2. Anestesia local com lidocaína 2%.
3. Punção da veia subclávia direita com agulha própria do kit.
4. Introdução do fio-guia através da agulha.
5. Retirada da agulha e passagem do dilatador.
6. Introdução do cateter venoso central sobre o fio-guia.
7. Retirada do fio-guia.
8. Teste de fluxo e refluxo sanguíneo positivo em ambas as vias.
9. Fixação do cateter com fio de nylon 3-0.
10. Realizado curativo estéril no local.
11. Solicitada radiografia de tórax para controle do posicionamento do cateter e avaliação de possíveis complicações.</pre>
            </div>

            <div class="item">
                <h3>Drenagem de Tórax</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DRENAGEM DE TÓRAX:

1. Realizadas assepsia e antissepsia com clorexidina alcoólica.
2. Colocação de campos estéreis.
3. Anestesia local com lidocaína 2%.
4. Incisão e diérese com bisturi.
5. Exploração e divulgação do local.
6. Colocação de dreno torácico e conexão com dreno de selo d'água.
7. Teste positivo do dreno torácico.
8. Fixação com fio de nylon 3-0.
9. Curativo local.</pre>
            </div>

            <div class="item">
                <h3>Paracentese (Ascite)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>INDICAÇÕES DE PARACENTESE: ASCITE SEM DIAGNÓSTICO PRÉVIO. QUANDO JÁ TEM O DIAGNÓSTICO, MAS ESTÁ TRAZENDO MUITO DESCONFORTO AO PACIENTE. SE SUSPEITA DE PERITONITE BACTERIANA ESPONTÂNEA EM PACIENTES ALCOOLATRAS, POR EXEMPLO.

FAZER PUNÇÃO EM FOSSA ILÍACA ESQUERDA, ASSEPSIA, ANTISSEPSIA, LUVA ESTÉRIL, ANESTESIA 5-10ML DE LIDOCAINA 2%, FUGIR DE VASOS EPIGÁSTRICOS, ASPIRANDO E INJETANDO DESDE A PELE ATÉ O PERITONIO. TIRAR AGULHA E INSERIR ABOCATH 14 COM SERINGA, COLOCAR PERPENDICULARMENTE. IR INTRODUZINDO E ASPIRANDO. QUANDO CHEGAR LIQUIDO ASCITICO, PARAR DE PROGREDIR A AGULHA. EMPURRAR O CATETER E RETIRAR A AGULHA, TAMPAR COM O DEDO. PEGAR EQUIPO E JUNTAR AO FRASCO COLETOR PARA MENSURAR A QUANTIDADE DE LIQUIDO. NÃO DEIXAR DOBRAR O CATETER, PRENDER COM ESPARADRAPO. DRENAR 4 LITROS PARA NÃO REPOR ALBUMINA.</pre>
            </div>

            <div class="item">
                <h3>Cuidados com Feridas e Suturas</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ANTISSÉPSIA EXAUSTIVA + ANALGÉSIA + SUTURA + CURATIVO:

PRESCREVO SINTOMÁTICOS
1. ORIENTO RETIRADA DE PONTOS EM UBS, NESTA UNIDADE (DAS 08H -11H) OU COM PROFISSIONAL DE SAÚDE CAPACITADO EM 7 -10 DIAS. 
2. TROCA DE CURATIVO DIÁRIA EM UBS OU NESTA UNIDADE (08H – 11H). 
3. ORIENTO CUIDADOS DE HIGIENE, LAVAR FERIMENTO DIARIAMENTE COM ÁGUA E SABÃO NEUTRO APENAS. 
4. ORIENTO SINAIS DE ALARME - VERMELHIDÃO, DOR PROGRESSIVA, SECREÇÃO PURULENTA - RETORNO IMEDIATO CASO INTERCORRÊNCIA OU SE JULGAR NECESSÁRIO.

# ACIDENTE COM PREGO/FERRO/MORDIDA DE ANIMAL DOMÉSTICO:
1. REALIZAR CURATIVO DIARIAMENTE APÓS HIGIENE COM ÁGUA E SABÃO PROTEX OU GLICERINADO;
2. REALIZAR VACINA ANTITETÂNICA NA UBS APÓS ATENDIMENTO MÉDICO;
3. OBSERVAR ANIMAL DOMÉSTICO DURANTE 10 DIAS, EM CASO DE FUGA, MORTE OU MUDANÇAS DE COMPORTAMENTO, VOCÊ DEVERÁ REALIZAR ESQUEMA VACINAL ANTIRRÁBICO COMPLETO COM 04 DOSES NA UBS;
4. RETORNAR AO ATENDIMENTO SE DOR INTENSA LOCAL, FEBRE OU DEMAIS SINAIS DE ALARME ORIENTADOS DURANTE ATENDIMENTO.

USO TÓPICO:
1. NEBACETIN POMADA - 1 FR - PASSAR 2 VEZES AO DIA - 12/12 HORAS.
2. DERSANI - 1 FR - PASSAR 2 VEZES AO DIA - 12/12 HORAS.
3. REALIZAÇÃO DE CURATIVO - GAZES, ESPARADRAPO, PANO DE GAZES, SF 0,9%, SABONETE GLICERINADO OU PROTEX, FAIXAS PARA REALIZAÇÃO DE CURATIVOS - REALIZAR CURATIVO DE 12/12 HORAS.

# CUIDADOS:
- SINAIS VITAIS E CUIDADOS GERAIS De 4/4 horas 
- ORIENTO CUIDADOS DE HIGIENE EM FERIDA 
- LAVAR FERIMENTO DIARIAMENTE COM SF 0,9% E SABÃO NEUTRO (CLOREXIDINE) APENAS 
- REALIZAR CURATIVO EM FERIDA DIARIAMENTE APÓS HIGIENE LOCAL 
- PASSAR POMADA NEOMICINA+BACITRACINA E DERSANI ÓLEO CICATRIZANTE SEMPRE, POR FAVOR 
- DEPOIS UTILIZAR GAZES, PANO DE GAZES, ESPARADRAPO OU MICROPORE E FAIXAS PARA REALIZAÇÃO DE CURATIVO LOCAL 
- CUIDADOS COM CURATIVO - ORIENTO SINAIS/SINTOMAS DE ALARME E ALERTA 
- PROSTRACÃO, FEBRE, EDEMA, VERMELHIDÃO, SENSIBILIDADE AO TOQUE, DOR PROGRESSIVA E SECREÇÃO PURULENTA LOCAL EM FERIDA 
- RISCO DE INFECÇÃO RELACIONADO A PROCEDIMENTOS INVASIVOS SECUNDÁRIOS À ACESSOS INVASIVOS 
- DEVERÁ SER REALIZADA TROCA DE ACESSO VENOSO PERIFÉRICO A CADA 72 HORAS OU ANTES SE APRESENTAR SINAIS FLOGÍSTICOS 
- ANALGESIA 
- DEVIDO DOR AGUDA RELACIONADA A AGENTE ETIOLÓGICO LESIVO EVIDENCIADO POR EXPRESSÃO FACIAL DE DOR 
- MEDICAR CONFORME PRESCRIÇÃO MÉDICA De 6/6 horas</pre>
            </div>
        </div>

        <!-- ===================== IVAS & RESPIRATÓRIO ===================== -->
        <div id="ivas" class="section">
            <h2 class="section-title">IVAS & Respiratório</h2>

            <div class="item">
                <h3>Resfriado / Gripe / Tosse</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># RESFRIADO / GRIPE
USO NASAL:
1) Soro Fisiológico 0,9% --- 1 frasco - Lavar as narinas até 6x ao dia
2) Budesonida 50mcg --- 1 frasco - Aplicar 02 jatos em cada narina 12/12h, por 10 dias

USO ORAL:
1) Dipirona 500mg --- 1 caixa - Tomar 01 a 02 cp VO de 6/6h, se dor ou febre
2) Ibuprofeno 600mg --- 15 cp - Tomar 01 cp VO de 8/8h, por 5 dias 
3) Maleato de Dexclorfeniramina + Betametasona xarope --- 1 frasco - Tomar 10ml VO de 6/6h, por 5 dias
4) Decongex --- 1 caixa - Tomar 1 comprimido de 12/12h de 2 a 5 dias

# TOSSE
- Dropropizina 30mg/ml (Tosse seca): Tomar 30 gotas de 6/6h se tosse seca, suspender uso se tosse com catarro.
- Acetilcisteína 600 mg/5 g sachês: Diluir 01 sachê em ½ copo d'água em temperatura ambiente e tomar à noite antes de deitar, por 7 a 10 dias.
- Descon 12mg + 15mg: Tomar 01 cp VO de 12/12h, por 7 dias. Descon Xarope: Tomar 10ml de 6/6h, por 5 dias.
- Bromidrato de dextrometorfano 2 mg/ml: Tomar 10ml de 8/8h se tosse. (Ou 5-10 mL de 4/4 horas; ou 15 mL a cada 6-8 horas).</pre>
            </div>

            <div class="item">
                <h3>Amigdalite Bacteriana e Laringite</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># AMIGDALITE BACTERIANA 
USO ORAL:
1. AMOXICILINA 500MG + CLAVULANATO 125MG - 21 CP (Tomar 1 cp de 8/8h por 7 dias)
2. DIPIRONA 500MG - 20 CP (Tomar 1 cp de 6/6h se dor e/ou febre)
3. IBUPROFENO 600MG - 15 CP (Tomar 1 cp de 8/8 horas se dor - evitar usar por mais de 5 dias consecutivos)
4. PREDNISONA 20MG - 6 CP (Tomar 2 cp por dia, pela manhã, por 3 dias)

# LARINGITE
USO ORAL:
1. Fexofenadina 180 mg - Tomar 01 cp VO 1x ao dia, por 7 dias.
2. Prednisolona 40mg - Tomar 01 cp VO pela manhã, por 5 dias.
3. Dipirona 500mg - Tomar 01 a 02 cp VO, se dor ou febre.</pre>
            </div>

            <div class="item">
                <h3>Sinusite e Rinite</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># SINUSITE
USO ORAL:
1. Amoxicilina + Clavulanato 500 + 125 mg ---- 21 cp (Tomar 1cp VO de 8/8 horas, por 07 dias)
2. Dipirona 500mg ---- 1 caixa (Tomar 01 a 02 cp VO de 6/6h, se dor ou febre)
3. Prednisolona 20mg ---- 10 cp (Tomar 01 cp VO pela manhã, por 5 dias)
4. Acetilcisteína 40mg/ML Xarope - 1 FR (Tomar 10 ML, via oral, de 8 em 8 horas por 3 dias)

USO NASAL:
1) Soro Fisiológico 0,9% ---- 1 frasco (Lavar as narinas 4x ao dia)
2) Budesonida spray nasal 50mcg ---- 1 frasco (Aplicar 02 jatos em cada narina de 12/12h, por 10 dias)

# RINITE
Uso oral:
1. Lemont 10+5mg --- Tomar 01 cp VO por dia, por 14 dias
Uso Nasal:
1. Budesonida 50mcg --- Aplicar 02 jatos em cada narina 12/12h, por 10 dias</pre>
            </div>

            <div class="item">
                <h3>Asma (Ambulatorial e Crise)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ASMA (AMBULATORIAL)
USO INALATÓRIO:
1. Salbutamol 100mcg/dose aerossol spray --- 2 frascos (Inalar 4 jatos de 4/4 horas se dor no peito e/ou falta de ar. Aplicar 04 jatos de 6/6h, por 7 dias em caso de exacerbação)
2. Dipropionato de Beclometasona + Sulfato de Salbutamol (Clenil HFA 250 mcg) --- 2 frascos (Inalar 2 jatos pela manhã e 2 à noite)
USO ORAL:
1. Prednisona 20mg --- 10 cp (Tomar 01 cp VO pela manhã, por 7 dias em caso de crise/exacerbação)

# CRISE ASMÁTICA
- REALIZAR DE 4 A 10 PUFFS DE SALBUTAMOL 100MCG DE 20 EM 20 MINUTOS POR 1 HORA + PREDNISOLONA 50MG VO (1-2MG/KG ATÉ 40MG PARA CRIANÇAS). OU METILPREDNISOLONA 1 AMPOLA EV OU HIDROCORTISONA 1 AMPOLA EV
- MANTER SATURAÇÃO DE O2 ENTRE 93-95% EM CATETER DE O2
- REAVALIAR APÓS 01 HORA. ALTA SE SAT >93%
SE NÃO MELHORAR:
SULFATO DE MAGNÉSIO 2G EV, INFUNDIR EM 20 MINUTOS (10ML DE MGSO4 20% + 100ML DE SF0.9% EV EM 20MIN)
- TERBUTALINA ½ OU 1 AMPOLA É USADA EM CASO DE INDISPONIBILIDADE DE SALBUTAMOL, COMO ALTERNATIVA. PODE SER FEITA SUBCUTÂNEA OU MESMO INTRAMUSCULAR EM CASOS MAIS GRAVES.
- FENOTEROL OU SALBUTAMOL 10 A 20 GOTAS EM 5ML DE SF0.9% + 40 GOTAS DE BROMETO DE IPRATRÓPIO. 1 INALAÇÃO A CADA 20 MINUTOS POR 1 HORA.</pre>
            </div>
        </div>

        <!-- ===================== INFECTOLOGIA ===================== -->
        <div id="infecto" class="section">
            <h2 class="section-title">Infectologia Básica</h2>

            <div class="item">
                <h3>Gastroenterite (GEA)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># GASTROENTERITE 
USO ORAL:
1. Sais de Reidratação Oral --- 4 sachês (Diluir 1 sachê em 1 litro de água fervida/filtrada. Tomar 1 copo (250ml) após cada episódio de diarreia ou vômito)
2. Floratil (Saccharomyces boulardii) 200mg --- 1 caixa (Tomar 1 cápsula de 12/12 horas por 3 dias)
3. Metoclopramida 10mg (ou Ondansetrona 4mg/8mg) --- 1 caixa (Tomar 1 comprimido de 8/8 horas se náusea e/ou vômito)
4. Buscopan Composto (Dipirona 250mg + Escopolamina 10mg) --- 1 caixa (Tomar 1 comprimido de 8/8 horas se dor ou cólica abdominal)
5. Nitazoxanida 500mg --- Tomar 01 cp VO de 12/12h, por 3 dias (opção)

*** SE GEA INFECCIOSA (+5 dias / Febre / Sangue):
6. Ciprofloxacino 500mg --- 6 a 10 cp (Tomar 1 cp de 12/12 horas por 3 a 5 dias)</pre>
            </div>

            <div class="item">
                <h3>Cistite Simples (ITU)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># CISTITE SIMPLES 
USO ORAL:
1. Nitrofurantoína 100mg - 28 cp (Tomar 1 cp de 6/6h por 7 dias. Ou 1cp de 8/8h por 8 dias)
2. (Buscopan) Hioscina 10mg - 20 cp (Tomar 1 cp de 6/6h se dor em baixo ventre)
3. Dipirona 500mg - 20 cp (Tomar 1 cp de 6/6h se dor e/ou febre)
4. Fenazopiridina 200mg - 6 cp (OPCIONAL) (Tomar 1 cp de 8/8 horas, após a refeição, por até 2 dias - Lembrar que a urina pode ficar alaranjada)

*** OPÇÕES DE ATB SE ALERGIA/RESISTÊNCIA:
- Ciprofloxacino 500mg (1cp 12/12h por 5 dias)
- Fosfomicina (Monuril) 1 sachê (Dissolver em água e tomar dose única à noite)
- Amoxicilina 875 MG + Clavulanato 125 MG (Clavulin) – 1 CX (Tomar 1 CP de 8/8 horas durante 8 dias)</pre>
            </div>

            <div class="item">
                <h3>Pneumonia Comunitária (PAC)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># PNEUMONIA COMUNITÁRIA (Tratamento Ambulatorial)
USO ORAL:
1. Amoxicilina 500mg + Clavulanato 125mg --- 21 comprimidos (Tomar 01 comprimido de 8/8 horas por 07 dias)
2. Azitromicina 500mg --- 5 comprimidos (Tomar 01 comprimido uma vez ao dia por 05 dias)
3. Acetilcisteína 20mg/ml xarope --- 1 frasco (Tomar 10 ml a cada 8 horas por 3 a 5 dias)
4. Dipirona 500mg --- 10 comprimidos (Tomar 01 comprimido de 6/6 horas se dor ou febre)

- CLARITROMICINA 500MG - Tomar 1 comprimido, via oral, uma vez ao dia por 10 dias.
- SE AMBULATORIAL + COMORBIDADES, USO DE ATB NOS ULTIMOS 3 MESES, FR ALTERADA: MACROLIDEO (AZITRO/CLARITROMICINA) + BETALACTAMICO (AMOXI/CLAV).</pre>
            </div>

            <div class="item">
                <h3>Dengue (Grupos A, B, C, D)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DENGUE
USO ORAL:
1) Sais de Reidratação Oral --- 03 sachês (Diluir 01 sachê em 1L de água fervida/filtrada/mineral e tomar ao longo do dia)
2) Dipirona 500mg --- Tomar 01 a 02 cp VO de 6/6h, se dor ou febre
3) Paracetamol 750mg --- Tomar 01 cp VO de 6/6h, se dor ou febre
4) Escopolamina 10mg --- Tomar 01 cp VO de 8/8h, se dor abdominal
5) Metoclopramida 10mg --- Tomar 01 cp VO de 8/8h, se náuseas ou vômitos
6) Hidroxivina 25mg --- Tomar 01 cp VO de 8/8h, se coceira

** ATENÇÃO: NÃO TOMAR ANTI-INFLAMATÓRIOS (Nimesulida, Ibuprofeno, AAS, Diclofenaco, Cetoprofeno, Meloxicam, Piroxicam).

SINAIS DE ALARME: DOR ABDOMINAL, DESIDRATAÇÃO, SANGRAMENTOS, AUMENTO DE HT, QUEDA DE PLAQUETAS, SINAIS DE CHOQUE.
- GRUPO A (Sem comorbidades e Prova do laço negativa): Hidratação oral 60ml/kg/dia (1/3 de isotônicos ou SRO, 2/3 outros líquidos). Analgésicos. NENHUM ANTIINFLAMATORIO. Atento a sinais de alarme.
- GRUPO B (Comorbidades ou Petéquias na pele): Solicitar hemograma. SF0.9% de 500 a 1000ml EV. Observar HT. Se normal, alta. Retornar todos os dias para novo hemograma. Se subir mais de 10% passa para grupo C.
- GRUPO C (Sinais de alarme): SF0.9% 10ML/KG na primeira hora. Se melhorar, fase de manutenção: SF0.9% 25ML/KG em 6 horas. Após fazer solução de 1/3 SF0.9% + 2/3 SG5%: Realizar 25ML/KG em 8 horas. Alta se: melhora clínica importante, HT estável por 24h e plaquetas em ascensão acima 50.000.
- GRUPO D (Sinais de choque): Ressuscitação volêmica: 20ML/H de SF0.9% EM 20 MINUTOS. Repetindo 3x em 1 hora. Se melhorar, passar para grupo C. Se não melhorar: Albumina 20% 3ml/kg/h.</pre>
            </div>

            <div class="item">
                <h3>Escabiose, H. pylori e Anemia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ESCABIOSE
USO ORAL:
1. Ivermectina 6mg --- (Dose calculada) - Tomar 02 cp hoje e repetir a mesma dose em 07 dias.
2. Prometazina 25mg --- 10 cp - Tomar 01 cp à noite por 05 dias se coceira intensa.
USO TÓPICO: 
3. Permetrina 5% loção --- 3 a 5 frascos - À noite, após o banho, aplicar a loção em todo o corpo (poupando pescoço/cabeça) e dormir com ela. Na manhã seguinte retirar no banho. Repetir por 3 noites seguidas. Após 7 dias, repetir o uso por mais 3 noites.
* Orientação: Lavar todas as roupas de cama/banho e secar ao sol. Não compartilhar itens. Tratar familiares sintomáticos.

# TRATAMENTO H PYLORI
USO ORAL:
1. AMOXICILINA 500MG --- TOMAR 2 COMPRIMIDOS, VIA ORAL, DE 12 EM 12 HORAS POR 7 DIAS.
2. CLARITROMICINA 500MG --- TOMAR 1 COMPRIMIDO, VIA ORAL, DE 12 EM 12 HORAS POR 7 DIAS.
3. OMEPRAZOL 40MG --- TOMAR 1 COMPRIMIDO, VIA ORAL, DE 12 EM 12 HORAS POR 30 DIAS.

# ANEMIA FERROPRIVA
1. SULFATO FERROSO 40MG --- TOMAR 02 DRÁGEAS DE 08 EM 08 HORAS DURANTE 06 MESES.</pre>
            </div>
        </div>

        <!-- ===================== HAS / DM / CRÔNICAS ===================== -->
        <div id="has-dm" class="section">
            <h2 class="section-title">HAS, DM & Crônicas</h2>

            <div class="item">
                <h3>Hipertensão e Crise Hipertensiva</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># HIPERTENSÃO ARTERIAL - USO CONTÍNUO
USO ORAL:
1. ENALAPRIL 10 MG (ou Losartana 50mg) - Tomar 1 comprimido pela manhã e 1 à noite (12/12 horas).
2. ATENOLOL 25 MG (ou Metoprolol 25mg) - Tomar 1 comprimido pela manhã e 1 à noite (12/12 horas).
3. HIDROCLOROTIAZIDA 25 MG - Tomar 1 comprimido pela manhã.
4. SINVASTATINA 20 MG - Tomar 2 comprimidos à noite.

# CRISE E EMERGÊNCIA HIPERTENSIVA
PSEUDOCRISE HIPERTENSIVA: PACIENTE NÃO HIPERTENSO COM PICO PRESSÓRICO (ANSIEDADE, TRAUMA, DOR). NÃO PRESCREVER ANTI-HIPERTENSIVO. OU PACIENTE SABIDAMENTE HIPERTENSO QUE NÃO FAZ USO CORRETO DE MEDICAÇÃO, PODE FAZER AJUSTE DA MEDICAÇÃO E MANDAR EMBORA.
URGÊNCIA HIPERTENSIVA: HIPERTENSO (SISTÓLICA ACIMA DE 180) + SINTOMAS INESPECÍFICOS. EXCLUIR EDEMA DE PULMÃO, DISSECÇÃO AGUDA DE AORTA, IAM, IC DESCOMPENSADA. TTO: CLONIDINA (0,1 A 0,2MG PODENDO REPETIR A CADA 30MIN. COM DOSE MÁXIMA DE 0,6MG), CAPTOPRIL (25MG VIA ORAL!! ESPERAR 1H, FAZER +25MG. COM DOSE TOTAL EM 24H DE ATÉ 100MG). NÃO USAR FUROSEMIDA, NEM BETA BLOQUEADOR.
EMERGÊNCIA HIPERTENSIVA: PA > 180X120 + LESÃO DE ÓRGÃO ALVO. REDUZIR DE 20 A 25% EM 1 A 2 HORAS. TTO: NITROGLICERINA (TRIDIL - EFEITOS CORONARIANOS): 10ML + 240ML DE SF0.9%. 200MCG/ML. DOSE DE 5 A 100 MCG/KG/MIN. (5 a 60 ML/H). NITROPRUSSIATO DE SÓDIO (NIPRIDE - EFEITOS PERIFÉRICOS): 2ML + 248ML DE SG 5%. 200MCG/ML. DOSE DE 0,5 A 10 MCG/KG/MIN. NÃO USAR EM IAM.</pre>
            </div>

            <div class="item">
                <h3>Diabetes Mellitus e Insulina</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DIABETES MELLITUS - USO CONTÍNUO
USO ORAL:
1. METFORMINA 500 MG ou 850 MG - Tomar 1 comprimido após as refeições. (Iniciar sempre a noite. Se aumentar, adicionar pela manhã).
2. GLIBENCLAMIDA 5MG (MIN:2,5; MAX: 20 MG) - Tomar 1 comprimido em jejum ou antes das refeições.

USO SUBCUTÂNEO:
3. INSULINA NPH (0,3 a 0,5 U/kg/dia) - Aplicar SC, 2/3 da dose pela manhã e 1/3 da dose à noite.

# CORREÇÃO DE HGT NO PRONTO ATENDIMENTO (Insulina Regular SC):
Até 150 mg/dL: Não aplicar
151 a 200 mg/dL: Aplicar 02 UI
201 a 250 mg/dL: Aplicar 04 UI
251 a 300 mg/dL: Aplicar 06 UI
301 a 350 mg/dL: Aplicar 08 UI
351 a 400 mg/dL: Aplicar 10 UI
> 400 mg/dL: Aplicar 12 UI e procurar avaliação médica imediata.
* Se Hipoglicemia (< 70 mg/dL): 4 ampolas de Glicose 50% EV.

# HIPOGLICEMIA
30ML DE GLICOSE 50% E FAZER DIRETO EV LENTO!!!
OU SORO GLICOSADO + HIDROCORTISONA.
MANUTENÇÃO SE PACIENTE ESTIVER DESIDRATADO: SF0.9% + 50ML GLICOSE 50%.
SE CIRROTICO/ALCOOLATRA/DESNUTRIDO: ASSOCIAR TIAMINA 1 AMPOLA EV DIRETO.</pre>
            </div>

            <div class="item">
                <h3>Gota</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># GOTA
USO ORAL:
1. ALOPURINOL – A dose inicial é de 100 mg/dia, com aumento gradual de 100 mg a cada 2 a 4 semanas, atingindo dose mínima de 300 mg/dia. Deve-se aumentar a dose até atingir o alvo terapêutico (ácido úrico menor que 6 mg/dL ou menor que 5 mg/dL na presença de tofos) ou até a dose máxima de 800 mg.
2. COLCHICINA 0,5 MG – 8/8 HORAS SE DOR DEVIDO CRISE DE GOTA.

O que pode desencadear as crises de gota? Ingestão de álcool (vinho tinto e cerveja), dieta rica em purina, trauma físico, cirurgias, quimioterapia e uso de diurético.</pre>
            </div>
        </div>

        <!-- ===================== SINTOMÁTICOS ===================== -->
        <div id="sintomaticos" class="section">
            <h2 class="section-title">Analgesia & Sintomáticos</h2>

            <div class="item">
                <h3>Dor Muscular / Lombalgia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DOR MUSCULAR / LOMBALGIA (CID: M54.5)
USO ORAL:
1. Dipirona 500mg --- 1 caixa - Tomar 01 a 02 cps de 6/6 horas, se dor.
2. Ibuprofeno 600mg (ou Nimesulida 100mg / Cetoprofeno 150mg) --- 1 caixa - Tomar 01 cp de 8/8 horas (Nimesulida/Ceto de 12/12h) se dor forte, por até 5 dias.
3. Ciclobenzaprina 10mg (ou 5mg) --- 1 caixa - Tomar 01 comprimido à noite, por 5 dias.
4. Paco (Paracetamol 500mg + Codeína 30mg) --- 1 caixa - Tomar 01 cp de 8/8 horas SE DOR INTENSA refratária.

* Prescrição Imediata (PS): Dexametasona 4mg IM + Cetoprofeno 50mg/ml IM.
* Opções: Diclofenaco sódico 50mg (1cp 12/12h por 5 dias), Nimesulida 100mg (1cp 12/12h por 5 dias).
* Betametasona 1 AMPOLA IM (Corticoide de depósito por 30 dias).
* Coltrax IM (Tiocolchicosídeo): Dores musculares da coluna decorrentes de contraturas.</pre>
            </div>

            <div class="item">
                <h3>Enxaqueca e Cefaleia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ENXAQUECA / CEFALEIA (CID: G43.0)
USO ORAL:
1. Naproxeno 500mg (ou 550mg) --- 1 caixa - Tomar 01 comprimido de 12/12 horas por até 5-7 dias se dor.
2. Doralgina (ou Dipirona 500mg) --- 1 caixa - Tomar 01 a 02 cps de 6/6 horas, se dor.
3. Sumatriptana 50mg (ou Naratriptana 2,5mg) --- 1 caixa - Tomar 01 cp quando perceber sinais iniciais de enxaqueca. Se resposta parcial, usar novo cp após, no mínimo, 2 horas.
4. Metoclopramida 10mg --- 1 caixa - Tomar 01 cp VO de 8/8h, se náuseas ou vômitos associados.

* Prescrição para agora (PS): Tramal 50mg/ml EV Agora. Obs: lembrar que costuma causar muita náusea e vômito, sempre associar antiemético.</pre>
            </div>

            <div class="item">
                <h3>Vertigem / Labirintite</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># VERTIGEM / LABIRINTITE
USO ORAL:
1. Betaistina (Labirin/Betina) 24mg (ou 8mg) --- 1 caixa - Tomar 01 cp pela manhã (ou de 8/8 horas para a de 8mg).
2. Flunarizina (Vertix) 10mg --- 1 caixa - Tomar 01 cp à noite por 10 a 14 dias.
3. Ibuprofeno 600mg --- 1 caixa - Tomar 1 cp de 8/8 horas se dor.
4. Prednisona 20mg --- 10 cp - Tomar 1 cp de 12/12 horas por 5 dias (se quadro inflamatório associado).

* Prescrição Crise (PS): Dimenidrinato + Piridoxina (Dramin B6) EV/IM.
* Outras opções: Cinarizina 75 mg (1 cp ao dia) - Distúrbios circulatórios. Meclin 25 mg (1cp 12/12 h) - Distúrbios equilíbrio, náuseas/vômitos.</pre>
            </div>

            <div class="item">
                <h3>Constipação e Sintomáticos Gerais</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># CONSTIPAÇÃO / OBSTIPAÇÃO (CID: K59)
USO ORAL:
- ÓLEO MINERAL: Tomar 15 ML (uma colher de sopa) de 08 em 08 horas por 10 dias.
- LACTULOSE 667MG/ML: Tomar 15ML, via oral, de 12 em 12 horas por 10 dias.
- SAIS DE REIDRATAÇÃO ORAL: Dissolver 1 sachê em 1 litro de água e ingerir sempre que possível.

# SINTOMÁTICOS GERAIS
USO ORAL:
1. Dipirona 500mg --- 1 caixa - Tomar 01 a 02 cps de 06/06 horas, se dor ou febre
2. Paracetamol 500mg --- 1 caixa - Tomar 01 a 02 cps de 06/06 horas, se dor ou febre
3. Ibuprofeno 600mg --- 15 cp - Tomar 01cp de 08/08 horas se dor forte, por até 05 dias
4. Metoclopramida (Plasil) 10mg (ou Ondansetrona 8mg) --- 1 caixa - Tomar 01cp de 08/08 horas, se náuseas ou vômitos
5. Escopolamina (Buscopan) 10mg --- 1 caixa - Tomar 01cp de 06/06 horas, se dor abdominal tipo cólica
6. Simeticona (Luftal) 40mg --- 1 caixa - Tomar 01cp de 08/08 horas se distensão/gases
7. Omeprazol 20mg --- 1 caixa - Tomar 01cp/dia, pela manhã, em jejum</pre>
            </div>
        </div>

        <!-- ===================== OFTALMO / OTO ===================== -->
        <div id="oftalmo-oto" class="section">
            <h2 class="section-title">Oftalmologia & Otorrino</h2>

            <div class="item">
                <h3>Conjuntivite e Oftalmológicos</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># DOR/HIPEREMIA EM OLHOS - CONJUNTIVITE
USO OCULAR/OFTALMOLÓGICO: 
1. CILODEX (Cloridrato de Ciprofloxacino 3,5 mg/ml + Dexametasona 1 mg/ml) - 1 frasco - Pingar 3 gotas no olho afetado de 6/6 horas por 7 dias. 
2. CLORIDRATO DE TETRACAÍNA 10 MG/ML + CLORIDRATO DE FENILEFRINA 1MG/ML 10 ML COLÍRIO ANESTÉSICO - 1 FRASCO - Pingar 3 gotas no olho afetado de 3/3 horas se dor.
3. LUBRIFICANTE OFTÁLMICO COLÍRIO - 1 FRASCO - Pingar 3 gotas no olho afetado de 3/3 horas se dor.

# OUTRAS OPÇÕES OFTALMOLÓGICAS
- Tobramicina oftalmológica 3mg/ml – colírio: Aplicar 01-02 gotas de 04/04 horas no olho afetado.
- Tobramicina + dexametasona oftalmológico (3mg/ml + 1mg/ml) – colírio: Aplicar 01 a 02 gotas de 06/06 horas no olho afetado.
- Relestat colírio (1gt 2x/dia por 5 dias)
- Garasone (3mg+1mg) 20ml (Gentamicina + Betametasona)
- Cotorolaco 5m (AINES) / 1 gota 4x ao dia.
- Tobradex/Tobracort colírio: 1gt 4x ao dia por 7 dias.</pre>
            </div>

            <div class="item">
                <h3>Otites e Otológicos</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># OTITE EXTERNA
USO OTOLÓGICO:
1. Otociriax --- Aplicar 4 gotas na orelha afetada de 12/12h por 7 dias.
2. Otosporin --- Aplicar 4 gotas na orelha afetada de 08/08 horas por 7 dias.

# OUTRAS OPÇÕES OTOLÓGICAS
- Otosyalar, Oto xilodase, Otosylase: 3gts 4x/dia.
- Se perfuração MT, usar CILODEX colírio.
- Se infecção FÚNGICA, usar Ác. acético 2% ou Álcool boricado 3% (5ml).

# IVAS BACTERIANA (Faringoamigdalite/Sinusite/OMA)
Uso Oral:
1. Amoxicilina 500mg --- Tomar 01 cp de 08/08 horas por 10 dias
2. Amoxicilina + Clavulanato (500 + 125 mg) --- 1 cp de 8/8 horas por 07 dias. (875 + 125 mg) --- 1 cp de 12/12h por 07 dias
3. Uso IM: Benzetacil 1.2 milhão UI dose única</pre>
            </div>
        </div>

        <!-- ===================== PEDIATRIA ===================== -->
        <div id="pediatria" class="section">
            <h2 class="section-title">Pediatria (Urgências)</h2>

            <div class="item">
                <h3>Bronquiolite Pediátrica</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>BRONQUIOLITE (PESO: 12 KG)
1. DIETA ZERO
2. ACESSO CALIBROSO SALINIZADO
3. SF 0,9% 100ML EV 12/12H
4. CLAVULIN 500MG/100MG -> DILUIR 1 FA EM AD 10 ML -> FAZER 7,2 ML EV BOLUS LENTO (D0-7)
5. METIL-PREDNISOLONA 500 MG -> DILUIR 1 FA EM 8 ML DE DILUENTE PROPRIO -> ADM 0,1 ML EV 12/12HR
6. ATROVENT 4 GOTAS + SF 0,9% 5 ML VIA INALATÓRIA 6/6HRS
7. SALBUTAMOL 2 JATOS CADA 4 HORAS
8. DIPIRONA 0,2 ML EV 6/6 HORAS SE FEBRE OU DOR
9. NAUSEDRON 0,3 ML EV 08/08H SE NÁUSEAS
10. GLICOSE 25% + AD 10 ML EV SE HGT < 60MG/DL
11. MONITORIZAÇÃO CONTÍNUA DE SATURAÇÃO E FREQUENCIA CARDIACA
12. SINAIS VITAIS 03/03H + GLICEMIA CAPILAR 06/06H
13. LAVAGEM NASAL SF 0,9% 10ML EM CADA NARINA 01/01H SE NECESSARIO
14. O2 SUPLEMENTAR SE SATO2AA <94% E/OU DESCONFORTO RESPIRATÓRIO 0,5LT/MIN</pre>
            </div>

            <div class="item">
                <h3>Pneumonia Pediátrica (PNM)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>PNM PEDIATRIA (PESO: KG)
1. DIETA GERAL PARA IDADE
2. ACESSO CALIBROSO SALINIZADO
3. CLAVULIN ___ MG DE 8/8 HORAS + SF 100 ML EV
4. DIPIRONA ___ ML EV DE 6/6 HORAS SE DOR OU FEBRE
5. ONDANSETRONA ___ ML EV DE 8/8 HORAS SE NAUSEA OU VOMITO
6. SINAIS VITAIS 06/06 HRS
7. LAVAGEM NASAL SF 0,9% 10ML EM CADA NARINA 01/01H SE NECESSARIO (OBSTRUÇÃO NASAL)
8. O2 SUPLEMENTAR COM CATETER NASAL SE SATO2 AA <94% E/OU DESCONFORTO RESPIRATÓRIO
9. CUIDADOS GERAIS E COMUNICAR PLANTONISTA SE INTERCORRÊNCIAS</pre>
            </div>

            <div class="item">
                <h3>Crise Convulsiva Pediátrica</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>CONVULSÃO PEDIATRIA (PESO: KG)
1. DIETA ZERO
2. ACESSO CALIBROSO SALINIZADO
3. SF 0,9% 100ML EV 12/12H
4. DIAZEPAM 5MG/ML 0,06ML/KG EV 10/10MIN (REPETIR DOSE ATÉ 3 VEZES)
5. MIDAZOLAM 5MG/ML 0,04ML/KG EV 10/10MIN (REPETIR DOSE ATÉ 3 VEZES)
6. FENITOÍNA 50 MG/ML 0,4ML/KG + SF 0,9% 100 ML EV INFUNDIR EM 30 MINUTOS
7. FENOBARBITAL 100 MG/ML 0,2 ML/KG + SF 0,9% 100 ML EV INFUNDIR EM 30 MINUTOS
8. DIPIRONA 0,05ML/KG EV 06/06H SE FEBRE OU DOR
9. NAUSEDRON 0,075ML/KG EV 08/08H SE NÁUSEAS
10. GLICOSE 25% + AD 10 ML EV SE HGT < 60MG/DL
11. MONITORIZAÇÃO CONTÍNUA DE SATURAÇÃO E FC
12. SINAIS VITAIS 03/03H E GLICEMIA CAPILAR 06/06H
13. O2 SUPLEMENTAR SE SATO2AA <94% E/OU DESCONFORTO RESPIRATÓRIO</pre>
            </div>
        </div>

        <!-- ===================== MACETES PEDIATRIA ===================== -->
        <div id="macetes-ped" class="section">
            <h2 class="section-title">Macetes de Pediatria (Tabelas)</h2>

            <div class="item">
                <h3>Doses Rápidas e Fórmulas</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>SUGESTÕES DE DOSES EM PEDIATRIA ATRAVÉS DE DICAS E MACETES!

# ANALGÉSICOS/ANTITÉRMICOS
- DIPIRONA Gotas 500mg/ml: 1 gota/kg/dose 6/6hs (máx.: 40gotas/dose)
- DIPIRONA Injetável: Peso + 20 = dose em ml IV/EV (máx.: 2ml)
- IBUPROFENO Gotas 50mg/ml: 2 gotas/Kg/dose até de 6/6hs
- IBUPROFENO Gotas 100mg/ml: 1 gota/Kg/dose até de 6/6hs (máx.: 40gts/dose)
- PARACETAMOL Gotas 200mg/ml: 1 gota/Kg/dose 4/4 ou 6/6hs (máx.: 50gts/dose)

# ANTIALÉRGICOS
- DEXCLORFENIRAMINA 2mg/5ml: Peso + 4 = dose em ml 8/8hs 5 dias (máx.: 5ml/dose)
- PROMETAZINA Injetável 50mg/2ml: Peso x 0,02 = dose em ml IM. (máx.: 2ml)

# ANTIBIÓTICOS
- AMOXICILINA 250mg/5ml: Peso + 3 = dose em ml 8/8hs 7 a 14 dias (máx.: 10ml/dose)
- AMOXICILINA + CLAVULANATO 250 + 62,5mg/5ml: Peso + 4 = dose em ml 8/8hs 7 a 14 dias (máx.: 10ml/dose)
- CEFALEXINA 250mg/5ml: Peso + 4 = dose em ml 6/6hs 7 a 14 dias (máx.: 10ml/dose)
- AZITROMICINA (Azit, Astro): Peso + 4 = dose em ml 1x/dia 3-5 dias. (Vide Tabela)

# ANTIEMÉTICOS
- DIMENIDRATO Gotas 25mg/ml: 1 gota/kg/dose 6/6hs SN. (máx.: 40gotas/dose)
- METOCLOPRAMIDA Gotas 4mg/ml: 2/3 PESO = dose em gotas 8/8hs SN (máx.: 40gotas/dose)
- METOCLOPRAMIDA Injetável 10mg/2ml: PESO + 20 = dose em ml IV/EV (máx.: 2ml)

# ANTIESPAMÓDICOS
- ESCOPOLAMINA + DIPIRONA (Buscopan Composto): 1 gota/kg/dose 6/6hs SN (máx.: 40gotas/dose)

# CORTICÓIDES
- DEXAMETASONA Elixir: Peso + 3 = ml/dose 8/8hs 3 a 5 dias. (máx.: 15ml/dose)
- DEXAMETASONA 4mg/ml: 0,3mg/kg/dose IM ou EV (máx.: 4mg/dose)
- HIDROCORTISONA 100 e 500 mg: 5mg/kg (ASMA) e 10mg/kg (ALERGIA).
- PREDNISOLONA 3mg/ml: Peso + 6 = dose em ml 12/12hs 5 dias. (máx.: 20ml/dia)

# XAROPES/ASMA
- SALBUTAMOL Xarope 2mg/5ml: Vide Tabela</pre>
            </div>
        </div>

        <!-- ===================== GINECOLOGIA ===================== -->
        <div id="gineco" class="section">
            <h2 class="section-title">Ginecologia & ISTs</h2>

            <div class="item">
                <h3>Vulvovaginites, Cervicites e DIP</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># VULVOVAGINITES E CERVICITES
> Vaginose Bacteriana (Gardnerella)
- Odor fétido (peixe podre) que piora com relação sexual/menstruação. Leucorreia acinzentada, bolhosa.
- Metronidazol 500mg 12/12h por 7 dias. (Opção: Clindamicina)

> Candidíase (Candida)
- Prurido, disúria, lesões de coçadura. Placas brancas/"coalhada".
- Fluconazol 150mg VO, dose única (Se não melhorar: usar 1 cp por semana por 6 meses).
- Miconazol ou Nistatina pomada.

> Tricomoníase (Trichomonas - DST)
- Prurido, corrimento amarelo-esverdeado bolhoso, colo em framboesa.
- Metronidazol 2g VO, dose única (ou 500mg 12/12h VO por 7 dias). Tratar parceiro e abstinência sexual.

> Cervicite (Gonococo e Clamídia)
- Ceftriaxona 500mg IM dose única + Azitromicina 1g VO dose única (ou Doxiciclina VO 7 dias).

# DOENÇA INFLAMATÓRIA PÉLVICA (DIP)
DIAGNÓSTICO: 3 Maiores + 1 Menor OU 1 Elaborado.
- Maiores: Dor hipogástrica, dor anexial, dor à mobilização do colo.
- Menores: Febre, leucocitose, PCR aumentado, cervicite.

TRATAMENTO AMBULATORIAL (Estágio 1 - sem peritonite):
- Ceftriaxona 500mg IM dose única + Metronidazol 250mg (ou 500mg) 12/12h VO por 14 dias + Doxiciclina 100mg 12/12h VO por 14 dias.
* Reavaliar em 48 a 72 horas. Gestantes, imunocomprometidos e estágios 2, 3 e 4 exigem tratamento hospitalar.</pre>
            </div>

            <div class="item">
                <h3>Úlceras Genitais e Menorragia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ÚLCERAS GENITAIS
> Herpes Simples (Múltiplas, dolorosas, base limpa)
- Aciclovir 400mg de 8 em 8 horas por 7 dias.

> Cancro Mole (Múltiplas, dolorosas, base suja/com pus)
- Azitromicina 1g VO dose única OU Ceftriaxona 500mg IM. Tratar parceiro.

> Sífilis (Única, indolor, cancro duro)
- Penicilina Benzatina (Benzetacil) 2.400.000 UI IM dose única (se sífilis primária).

# MENORRAGIA
Uso Oral:
1. Ácido Tranexâmico 250mg --- Tomar 03cp de 8/8 horas por 5 dias
2. Ibuprofeno 600mg --- Tomar 01cp de 08/08 horas por até 05 dias
3. Escopolamina 10mg --- Tomar 01cp de 06/06 horas se cólicas

- Paciente mulher em idade fértil com sgto e/ou corrimento vaginal: descartar gestação!
- Metronidazol pode ser dado via intravaginal/creme tópico em gestantes. Obs: lembrar que não pode usar álcool durante o TTO com imidazólicos.</pre>
            </div>
        </div>

        <!-- ===================== OBSTETRÍCIA ===================== -->
        <div id="obstetricia" class="section">
            <h2 class="section-title">Obstetrícia (Rotina e Urgência)</h2>

            <div class="item">
                <h3>Rotina Gestante e Infecções</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># EXAMES GESTANTES
PRIMEIRO TRIMESTRE: Hemograma, Coagulograma, Tipagem Sanguínea, Fator Rh, Coombs Indireto, Glicemia de jejum, Urina 1, Urocultura, VDRL, Anti-HIV, Toxoplasmose IgG e IgM, Hepatite B (HBsAg), USG obstétrica.
COMPLEMENTOS: Ácido fólico 400mcg até 12 semanas. Sulfato ferroso das 12 semanas até 60 dias de pós-parto. Vacinas: 3 doses Hep B, Influenza, Covid-19, 3 doses DT (DTpa a partir de 20 semanas).
24 A 28 SEMANAS: TOTG + repetição dos exames do 1º tri.
35 A 37 SEMANAS: Pesquisa de Estreptococo do grupo B.

# INFECÇÃO TRATO URINÁRIO NA GESTANTE
- Profilaxia: Cranberry 400mg 2x ao dia + Vitamina C 100mcg/dia. 2L de água, esvaziamento vesical.
- Tratamento ATB: Amoxi-Clav por 5 a 7 dias; Nitrofurantoína 100mg 6/6h por 5 dias; Cefuroxima 250mg 8/8h por 5 a 7 dias; Fosfomicina 1g dose única.

# TOXOPLASMOSE NA GESTANTE
- Se IgM e IgG reagentes: Solicitar teste de avidez de IgG (apenas até 16 semanas).
  * Baixa avidez (<30%): Infecção aguda. * Alta avidez (>60%): Infecção pregressa.
- Conduta (Aguda): Espiramicina (Até 16s: 500mg 2cps de 8/8h). Repetir exame em 15 dias.
  * >16s: Pirimetamina + Sulfadiazina + Ácido Folínico.

# DIABETES GESTACIONAL
- Metas HGT: Jejum < 92 | 1h pós-prandial < 180 | 2h pós-prandial < 153.
- Tratamento: Insulina 0,5 UI/kg/dia (2/3 pela manhã e 1/3 à noite). Ajustes a cada 15 dias.

# HIPOTIREOIDISMO GESTACIONAL
- Alvo: TSH menor ou igual a 2,5. Tratamento: Levotiroxina 1 a 2 mcg/kg/dia em jejum pela manhã.</pre>
            </div>

            <div class="item">
                <h3>Hemorragia Pós-Parto (HPP)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># HEMORRAGIA PÓS-PARTO (HPP)
Profilaxia: 10UI de Ocitocina IM pós-parto, clampeamento do cordão após 60s.

CONDUTA INICIAL:
- Máscara de O2 8-10L/min, Trendelemburg, SVD.
- 2 Acessos calibrosos: 1g de Ácido Tranexâmico em 100ml de SF 0,9% em 10 min. (Cristaloides em seguida).
- Ocitocina: Inicialmente 5UI EV lento em 3 min -> Após 20 a 40 UI em 500ml SF a 250ml/h -> Manutenção a 125ml/h.
- Se não houver melhora do índice de choque após 1500ml de cristaloide: Transfusão (Hemácias O-).

CAUSAS (4 Ts):
1. TÔNUS (Atonia Uterina - 80%): Compressão bimanual (Hamilton) + Ocitocina + Metilergometrina 0,2mg IM 20/20min (evitar em HAS) + Misoprostol 800mcg retal.
2. TECIDO: Retenção/Acretismo (extração manual/curetagem ou histerectomia).
3. TRAUMA: Revisão de canal e sutura.
4. TROMBINA: Coagulopatias (transfusão específica).</pre>
            </div>

            <div class="item">
                <h3>Pré-Eclâmpsia e Eclâmpsia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># PRÉ-ECLÂMPSIA E CRISE HIPERTENSIVA (PAS = 160 ou PAD = 110)
- Conduta Inicial (< 34 sem): Decúbito lateral esquerdo, SVD, BCF 1/1h.
- Hidralazina 20mg (Diluir 1 ampola em 9ml de AD e aplicar 5ml de 20 em 20 min) + Betametasona 12mg IM 24/24h (2 dias).
- SULFATO DE MAGNÉSIO: 
  * Ataque: Diluir 8ml de Sulfato de Magnésio a 50% em 12ml de SF 0,9% IV em 20 gotas/min.
  * Manutenção: Diluir 10ml em 490ml de SF 0,9% IV 100ml/h por 24h (BIC).
- Monitorar: Diurese, reflexos patelares e FR a cada 4 horas.
- Antídoto (Intoxicação): 1 ampola de Gluconato de Cálcio 10% IV em bolus.

# ECLÂMPSIA (Convulsões)
- Manter via aérea pérvia (lateralizar cabeça, cânula de Guedel, O2, aspirar secreções).
- Administrar Sulfato de Magnésio (Ataque + Manutenção) e Hidralazina conforme protocolo acima.</pre>
            </div>
        </div>

        <!-- ===================== ORTOPEDIA ===================== -->
        <div id="ortopedia" class="section">
            <h2 class="section-title">Ortopedia & Trauma</h2>

            <div class="item">
                <h3>Incidências Radiográficas e Imobilizações</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># INCIDÊNCIAS DE RADIOGRAFIA
MÃOS E PÉS: FRENTE, PERFIL E OBLÍQUO
ESCAFOIDE: FRENTE E PERFIL, OBLÍQUO PRONADO E DESVIO ULNAR
PUNHO, COTOVELO, ANTEBRAÇO, PERNA, TORNOZELO, COLUNA: FRENTE E PERFIL
COLUNA CERVICAL: FRENTE, PERFIL E TRANSORAL
CLAVÍCULA: FRENTE E ZANCA
OMBRO: FRENTE VERDADEIRO, PERFIL ESCAPULAR E PERFIL AXILAR
ARCOS COSTAIS: FRENTE E OBLÍQUO
BACIA: FRENTE
QUADRIL: PERFIL
JOELHO: FRENTE, PERFIL E AXIAL

# TALAS E GESSO
- TALA BOTA OU SURO PODÁLICA: Indicada para algumas fraturas e pós-cirúrgico, entorse e luxação.
- TALA TUBO OU INGUINOMALEOLAR: Imobiliza o joelho, limitando movimentos de flexão e extensão.
- TALA INGUINO PODÁLICA: Provisória para fraturas de tíbia e patela.
- TALA HEMIPELVEPODÁLICA OU TALA SPICA: Imobilização de todo o fêmur até a cirurgia.
- TALA LUVA OU ANTEBRAQUIOPALMAR: Restringe os movimentos do punho.
- TALA BRAQUIAL OU ÁXILO PALMAR: Paralisa os movimentos do braço até acima do cotovelo.
- TALA PINÇA DE CONFEITEIRO: Para fraturas de úmero.
- FÉRULA METÁLICA: Retém o movimento das falanges.

- BOTA GESSADA SEM SALTO: Para fraturas, luxações ou entorse de tornozelo.
- BOTA GESSADA COM SALTO: Permite pisar no chão.
- SARMIENTO GESSADO OU PTB: Para fratura de tíbia.
- TUBO GESSADO OU INGUINO MALEOLAR GESSADO: Joelho imobilizado.
- LUVA GESSADA OU ANTEBRAQUIOPALMAR GESSADO: Sustém os movimentos do punho.

ENFAIXAMENTO:
- VELPEAU DE CREPOM: Imobilizador dos ombros. Usado em luxação de ombro.
- TIPOIA AMERICANA / TIPOIA SIMPLES: Para limitar movimentos do ombro e repouso dos membros superiores.
- COLAR CERVICAL: Para torcicolos e inflamações na região.</pre>
            </div>

            <div class="item">
                <h3>Prescrição: Fratura de Fêmur</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>FRATURA DE FÊMUR:
1. DIETA LEVE PARA HAS E DM
2. SF 0,9% 250 ML 06/06H EV
3. CABECEIRA ELEVADA 45º / 30º
4. CATETER NASAL DE O2 ATÉ 5L/MIN
5. OMEPRAZOL 01 AMP EV + DILUENTE PRÓPRIO
6. CLEXANE 40MG SC 01 VEZ AO DIA (CEDO)
7. TRAMADOL 50 MG SC SE DOR FORTE
8. DIPIRONA 1 AMP IV 6/6 HORAS SE FEBRE OU DOR
9. MORFINA 1ML + AD 9 ML - ADM 2ML SE DOR FORTE (INTERVALO MINIMO DE 04 EM 04 HORAS)
10. LASIX 01 AMP EV ACM SE CONGESTÃO 1X DIA (NÃO ADMINISTRAR SE PA< 110X70MMHG)
11. TRAÇÃO NO MID SE DOR INTRATÁVEL
12. ONDANSETRONA 01 AMPOLA EV SE NAUSEAS
13. INSULINA REGULAR SC PROT NÃO NEFROPATA (GLICOSE 50% 4 AMP IV SE HGT < 70MG/DL)
14. SINAIS VITAIS DE 6/6H + GLICEMIA CAPILAR 04/04H + CUIDADOS GERAIS
15. MEDICAÇÕES DE USO CONTÍNUO DA PACIENTE</pre>
            </div>
        </div>

        <!-- ===================== HIDROELETROLÍTICOS ===================== -->
        <div id="hidroeletroliticos" class="section">
            <h2 class="section-title">Distúrbios Hidroeletrolíticos</h2>

            <div class="item">
                <h3>Potássio (Hipercalemia e Hipocalemia)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>POTÁSSIO ALTO - HIPERCALEMIA
1. GLUCONATO DE CÁLCIO 10% 10ML + SG5% 100ML EV CORRER EM 10 MIN (Pode repetir a dose a cada 2 horas se ainda estiver com alterações no ECG).
2. GLICOSE 50% 100ML + 10UI DE INSULINA REGULAR EV CORRER EM 30 MIN.
3. FUROSEMIDA 20MG 2 AMPOLAS EV BOLUS.
4. DEXTRO 1/1H E G50% 30ML EV BOLUS SE HGT < 70.

POTÁSSIO BAIXO – HIPOCALEMIA
- XAROPE KCL 6% 15ML = 12 mEq
- KCL CÁPSULA 600MG: 8 mEq/cápsula
- KCL 19,1% 1 AMPOLA (10ML): 25 mEq de K
- KCL 10% 1 AMPOLA (10ML): 13,4 MEQ DE K

LEVE (3 a 3,4 mEq/L) e sem perdas ou alterações ECG: Dar 15ML de Xarope de KCL de 6 em 6 horas (20 a 80 mEq ao dia).
MODERADA OU GRAVE (< 3) OU SINTOMÁTICA: Reposição VO (40mEq 3 a 4x ao dia) + REPOSIÇÃO EV 20mEq em 2-3 horas.
- SF 0.9% 480ML + KCl a 10%. Velocidade de 10 a 20 mEq/hora se hipocalemia ameaçadora a vida.
- Correr 2 ampolas em SF 0,9% 500ml em 4 horas.</pre>
            </div>

            <div class="item">
                <h3>Sódio Baixo (Hiponatremia)</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>SÓDIO BAIXO - HIPONATREMIA (Grave de instalação súbita)
- SF 0.9% 445ML + NaCl 20% 55ML = SOLUÇÃO A 3% 500ML (510 mEq/L de Sódio).
- Cada 1ML/KG dessa solução aumenta 1 mEq/L na quantidade sérica do paciente.
Exemplo (70kg, Na 116): Fazer 70 ML dessa solução em 15 min. (Espera-se que vá para 117). Pode repetir mais duas vezes. 
- Correção de ATÉ 3 mEq na primeira hora. 
- ATENÇÃO: Corrigir no máximo 7 a 8 mEq em 24 horas!
- Homem: 3,5ml/kg de solução de NaCl a 3% em 24hs. Dosar Na+ sérico de 4/4hs. 
- Mulher: 3,0ml/kg de solução de NaCl a 3% em 24hs.</pre>
            </div>

            <div class="item">
                <h3>Reposição de Bicarbonato e Urgência Dialítica</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># REPOSIÇÃO DE BICARBONATO: 
150 ML DE BICARBONATO DE SÓDIO 8,4% + ÁGUA DESTILADA 850 ML (OU SF 0,9% OU SG 5%) : 1000 ML/24H EM BIC 41 ML/H (150MEQ/L).

# URGÊNCIA DIALÍTICA: 
- ACIDOSE: PH < 7,1 
- ELETRÓLITOS: HIPERCALEMIA SEVERA (>6,5) 
- INGESTA DE TÓXICOS COMO ALCOOL, DROGAS 
- SOBRACARGA DE VOLUME 
- UREMIA: ENCEFALOPATIA, PERICARDITE, CONVULSOES, DISFUNÇAO PLAQUETARIA (>200MG/DL)</pre>
            </div>
        </div>

        <!-- ===================== PEÇONHENTOS & PSIQUIATRIA ===================== -->
        <div id="peconhentos" class="section">
            <h2 class="section-title">Peçonhentos & Psiquiatria</h2>

            <div class="item">
                <h3>Soros - Ofídicos e Aracnídeos</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>EM CASOS DE ACIDENTES, LIGUE PARA CIT 0800 721 3000
(As ampolas devem ser diluídas em Solução Salina ou Glicosada 5% na proporção 1:2 ou 1:5, em gotejamento rápido)

# JARARACA E CRUZEIRA:
- TIPO DE SORO: Soro Antibotrópico (SAB) ou Antibotrópico-Crotálico (SABC) 
- LEVE: 4 ampolas | MODERADO: 8 ampolas | GRAVE: 12 ampolas

# CASCAVEL:
- TIPO DE SORO: SAB ou SABC 
- MODERADO: 10 ampolas | GRAVE: 20 ampolas

# CORAL VERDADEIRA:
- TIPO DE SORO: Soro Antielapídico 
- GRAVE: 10 ampolas

# ARMADEIRA:
- TIPO DE SORO: Soro Antiaracnídico (SAA)
- MODERADO: 5 ampolas | GRAVE: 10 ampolas

# ARANHA MARROM:
- TIPO DE SORO: SAA ou Soro Antiloxoscélico (SALox)
- MODERADO: 5 ampolas | GRAVE: 10 ampolas

# ESCORPIÃO AMARELO (O Preto costuma ser leve e sem soro):
- TIPO DE SORO: Soro Antiescorpiônico (SAEsc) ou SAA
- MODERADO: 2 a 3 ampolas | GRAVE: 4 a 6 ampolas

# LAGARTA TATURANA:
- TIPO DE SORO: Soro Antilonômico (SALon)
- MODERADO: 5 ampolas | GRAVE: 10 ampolas</pre>
            </div>

            <div class="item">
                <h3>Psiquiatria: Agitação, Alcoolismo e Drogas</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># AGITAÇÃO
- DIAZEPAM 10MG: 01 ampola IM de 04 em 04 horas. (Se EV: diluir em 10ml de SF0.9% e fazer lento).
- HALOPERIDOL 5MG: Fazer 01 ampola IM de 30 em 30 minutos (Contenção química).
- MIDAZOLAM 5MG/ML: Fazer bolus de 1 ml diluídos em 10ml de Água Destilada.
* Coquetel: 50mg Meperidina (1/2 ampola) + 200mg Fenobarbital + 10mg Diazepam.

# ALCOOLISMO (Abstinência / Intoxicação)
- Soro Glicosado a 50% 50ML EV se glicemia < 60.
- Soro Ringer Lactato 500ML EV.
- TIAMINA 100MG/ML: 1 ampola EV ou IM (Fazer ANTES da glicose em desnutridos/cirróticos).
- METOCLOPRAMIDA 10MG: Diluir 1 ampola em 10ml de AD e fazer EV.
- RANITIDINA 50MG: 1 ampola diluída no soro.

# PRESCRIÇÃO PSIQUIATRIA (INTERNAÇÃO)
1. DIETA LEVE, CONFORME ACEITAÇÃO
2. DIAZEPAM 10 MG 01 CP VO 12/12H
3. PROMETAZINA 01 AMP IM 12/12H SE AGITAÇAO
4. DRAMIN B6 01 AMPOLA EV 08/08H SE NÁUSEAS
5. HALOPERIDOL 01 AMPOLA IM - 08/08H E ACM
6. PARACETAMOL 40 GOTAS 6/6H SE FEBRE OU DOR
7. CONTENÇÃO NO LEITO SE HOSTILIDADE
8. GLICOSE 50% 4 AMP EV SE HGT < 70MG/DL
9. SINAIS VITAIS 06/06H + CUIDADOS GERAIS
10. SERTRALINA 1-0-0
11. NEOZINE GTS 0-0-4GTS
12. QUETIAPINA 50MG 0-0-1

# CLASSES DE PSICOFÁRMACOS E INTOXICAÇÕES
- Antidepressivos (IRS, Tricíclicos, IRSN, IRND, IMAO)
- Estabilizador de humor: Lítio, Ácido Valpróico, Carbamazepina, Topiramato.
- Benzodiazepínicos: Diazepam, Midazolam, Lorazepam, Clonazepam.
- Antipsicóticos: Haloperidol, Clorpromazina (Típicos); Risperidona, Olanzapina (Atípicos).
- Psicoestimulantes: Metilfenidato, Lisdexanfetamina.
- Intoxicação por Benzodiazepínicos: Flumazenil. Intoxicação por Opioides: Naloxone.
- Delirium Tremens (SAA): Tratar com Benzodiazepínicos. Surto Psicótico: Antipsicóticos + Benzodiazepínicos.</pre>
            </div>

            <div class="item">
                <h3>Alergia / Anafilaxia</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre># ALERGIA / ANAFILAXIA
ANAFILAXIA: REAÇÃO DE HIPERSENSIBILIDADE COM ENVOLVIMENTO DE 2 OU MAIS SISTEMAS.
- APLICAR 0,3 A 0,5 ML DE ADRENALINA 1MG/ML VIA INTRAMUSCULAR E REPETIR APÓS 15 MINUTOS SE NECESSÁRIO. (1 AMPOLA TEM 1ML!)
- FAZER ENTRE 250 E 500ML DE SORO GLICOSADO A 5%.
- FAZER 01 AMPOLA IV DE HIDROCORTISONA 500MG.
- DILUIR 01 AMPOLA DE RANITIDINA 50MG EM 20ML DE SORO GLICOSADO 5% IV.
- DILUIR 01 AMPOLA DE DIFENIDRAMINA 50MG EM 100ML DE SF0.9.
- APLICAR PROMETAZINA 50MG 01 AMPOLA IM.

USO ORAL:
- DEXAMETASONA 0,5MG --- TOMAR 01 COMPRIMIDO, VIA ORAL, DE 08 EM 08 HORAS POR 3 DIAS.
- DEXCLORFENIRAMINA 2MG --- TOMAR 01 COMPRIMIDO, VIA ORAL, DE 08 EM 08 HORAS POR 05 DIAS.</pre>
            </div>
        </div>

        <!-- ===================== ANTIBIÓTICOS ===================== -->
        <div id="antibioticos" class="section">
            <h2 class="section-title">Guia de Antibióticos Hospitalares</h2>

            <div class="item">
                <h3>Tratamento Hospitalar das Patologias Infecciosas</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>- CELULITE 
1° ESCOLHA: OXACILINA 2G EV 4/4H OU 6/6H. ALTERNATIVA: CLINDAMICINA 600 MG EV 8/8H. 

- DIP 
1° ESCOLHA: CEFUROXIME 750 MG EV 8/8H OU AMPICILINA/SULBACTAM 3G EV 6/6H + DOXICICLINA 100 MG 12/12H. ALTERNATIVA: CLINDAMICINA 900 MG EV 8/8H + GENTAMICINA 5MG/KG/DIA. OBSERVAÇÕES: MANTER O TRATAMENTO POR 14 DIAS. 

- ERISIPELA 
1° ESCOLHA: PENICILINA G 2-4 MILHÕES DE UI EV 4/4H OU 6/6H. ALTERNATIVA: CLINDAMICINA 600 MG EV 8/8H 

- GERMES MULTIRRESISTENTES 
1° ESCOLHA: POLIMIXINA B SEMPRE ASSOCIADA A CARBAPENÊMICO OU AMINOGLICOSÍDEO OU TIGECICLINA. OBSERVAÇÕES: ADEQUAR TERAPIA AO ANTIBIOGRAMA E DISCUTIR CASO COM O SCI. 

- GRIPE H1N1 
1° ESCOLHA: OSELTAMIVIR 75 MG VO 12/12H. OBSERVAÇÕES: TRATAMENTO POR 5 DIAS. NOME COMERCIAL: TAMIFLU. 

- INFECÇÃO INTRA-ABDOMINAL COMUNITÁRIA 
1° ESCOLHA: CEFUROXIMA 750 MG 8/8H + METRONIDAZOL 500 MG 8/8H. ALTERNATIVA: AMPICILINA/SULBACTAM 3G EV 6/6H. OBSERVAÇÕES: SE COLEÇÃO INTRA-ABDOMINAL, CONSIDERAR DRENAGEM CIRÚRGICA. 

- INFECÇÃO INTRA-ABDOMINAL HOSPITALAR 
1° ESCOLHA: PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: CEFEPIME 2G EV 8/8H + METRONIDAZOL 500 MG EV 8/8H. OBSERVAÇÕES: SE COLEÇÃO INTRA-ABDOMINAL, CONSIDERAR DRENAGEM CIRÚRGICA. 

- MENINGITE 
1° ESCOLHA: CEFTRIAXONA 2G EV 12/12H. ALTERNATIVA: SE ALERGIA: VANCOMICINA 1G EV 12/12H. OBSERVAÇÕES: SE MAIOR DE 50 ANOS, ASSOCIAR AMPICILINA 2G EV 4/4H. 

- NEUTROPENIA FEBRIL 
1º ESCOLHA: PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: CEFEPIME 2G EV 8/8H. OBSERVAÇÕES: SE SUSPEITA DE GRAM-POSITIVO RESISTENTE, ASSOCIAR VANCOMICINA. 

- PÉ DIABÉTICO 
1º ESCOLHA: AMPICILINA/SULBACTAM 3G EV 6/6H. ALTERNATIVA: PIPERACILINA/TAZOBACTAM 4,5G 6/6H. 

- PIELONEFRITE AGUDA 
1º ESCOLHA: CEFUROXIMA 750 MG 8/8H. ALTERNATIVA: AMPICILINA/SULBACTAM 3G EV 6/6H OU CIPROFLOXACINO 400 MG 12/12H. OBSERVAÇÕES: SE GESTANTE: CEFALEXINA 500 MG 1 COMPRIMIDO VO 6/6H.

- PIELONEFRITE HOSPITALAR 
1º ESCOLHA: PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: CEFEPIME 2G EV 8/8H. OBSERVAÇÕES: ADEQUAR TRATAMENTO CONFORME ANTIBIOGRAMA. 

- PNEUMONIA COMUNITÁRIA 
1º ESCOLHA: AZITROMICINA 500 MG VO 1X/DIA + CEFUROXIMA 750 MG EV 8/8H OU AMPICILINA/SULBACTAM 3G EV 6/6H. ALTERNATIVA: SE INDICAÇÃO DE UTI: AZITROMICINA 500 MG EV 1X/DIA + CEFEPIME 2G EV 12/12H. OBSERVAÇÕES: AVALIAR TROCA PARA TRATAMENTO VO SE MELHORA CLÍNICA APÓS 72 HORAS E CONSIDERAR ALTA HOSPITALAR. O TRATAMENTO COM AZITROMICINA É POR 5 DIAS E OS DEMAIS POR 10 DIAS. 

- PNEUMONIA NOSOCOMIAL 
1º ESCOLHA: PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: CEFEPIME 2G EV 8/8H. OBSERVAÇÕES: AVALIAR ASSOCIAÇÃO COM VANCOMICINA 1 G EV 12/12H SE NÃO HOUVER MELHORA APÓS 48H DE TRATAMENTO. 

- SEPSE COMUNITÁRIA SEM FOCO DEFINIDO 
1º ESCOLHA: AMPICILINA/SULBACTAM 3G EV 6/6H OU PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: CEFEPIME 2G EV 8/8H + METRONIDAZOL 500 MG EV 8/8H. OBSERVAÇÕES: COLETAR CULTURAIS ANTES DO INÍCIO DOS ANTIMICROBIANOS E BUSCAR FOCO INFECCIOSO. 

- SEPSE HOSPITALAR SEM FOCO DEFINIDO 
1º ESCOLHA: VANCOMICINA 1G EV 12/12H + PIPERACILINA/TAZOBACTAM 4,5G 6/6H. ALTERNATIVA: VANCOMICINA 1G EV 12/12H + MEROPENEM 2 G EV 8/8H. OBSERVAÇÕES: AVALIAR USO DE POLIMIXINA B SE MULTIRRESISTENTE E ADEQUAR TERAPIA CONFORME CULTURAIS E ANTIBIOGRAMA.</pre>
            </div>
        </div>

        <!-- ===================== EXAMES DE IMAGEM ===================== -->
        <div id="exames-img" class="section">
            <h2 class="section-title">Laudos & Exames de Imagem</h2>

            <div class="item">
                <h3>Interpretação de ECG</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>ELETROCARDIOGRAMA: 
RITMO SINUSAL (D1, D2 E AVF ONDA P POSITIVA. ONDA P PRECEDE TODO QRS. TODO INTERVALO R-R É REGULAR). 
FC (CONTAR QUANTIDADE DE INTERVALOS R-R) 
ONDA P (COMPRIMENTO MAXIMO DE 3 QUADRADINHOS MENORES. ALTURA DE NO MAXIMO 2,5 QUADRADINHOS MENORES). POSITIVA EM D1 E AVF. 
INTERVALO P-R (NORMAL ENTRE 3 E 5 QUADRADINHOS). 
COMPLEXO QRS (NORMAL QUANDO TEM ATE 3 QUADRADINHOS). 
SEGMENTO ST NIVELADO COM A LINHA DE BASE DO ECG (INFRA -SIGNIFICATIVO QUANDO MAIOR OU IGUAL A 0,5MM- OU SUPRADESNIVELAMENTO –QUANDO TIVER 1MM OU MAIS COM EXCEÇÃO DE V2 E V3-). PODE TER DESNIVELAMENTO EM V1 E V2. 
ONDA T ASSIMETRICA E PODE SEGUIR DIREÇÃO DO QRS E TEM DE ALTURA +/- 30% DA ALTURA DO QRS. POSITIVA EM D1, D2 E AVF. OBRIGATORIAMENTE POSITIVA EM V5 E V6. 

- SOBRECARGA ATRIAL DIREITA: ONDA P MAIS AMPLA, PONTIAGUDA E SIMETRICA. 
- SOBRECARGA ATRIAL ESQUERDA: ONDA P MAIS ACHATADA E ALONGADA. MAIS DE 2,5MM. SINAL DE MORRIS. COMUM EM PACIENTES COM HAS. 
- SOBRECARGA VENTRICULAR DIREITA: QRS NEGATIVO EM D1. COMUM EM TEP. S1Q3T3 
- SOBRECARGA VENTRICULAR ESQUERDA: CRITERIOS DE ROMHILT. 

CRITÉRIOS ELETROCARDIOGRÁFICOS DE IAM COM SUPRA DE ST:
- Presença de supradesnivelamento do segmento ST em pelo menos duas derivações contíguas (≥ 1 mm em todas as derivações, exceto V2 e V3, onde se aplicam os seguintes pontos de corte: ≥ 2,5 mm em homens com menos de 40 anos, ≥ 2 mm em homens acima de 40 anos e ≥ 1,5 mm em mulheres).
- Presença de infradesnivelamento do segmento ST em V1-V3 pode sugerir IAM posterior.
- Presença de bloqueio completo do ramo esquerdo (BRE) novo ou presumivelmente novo.</pre>
            </div>

            <div class="item">
                <h3>Radiografia, USG e TC</h3>
                <button class="copy-btn" onclick="copyText(this)">Copiar</button>
                <pre>RADIOGRAFIA: RADIOPACO X RADIOLÚCIDO (PRETO) 
USG: OPOECOICO X HIPERECOICO 
TC: HIPODENSO X HIPERDENSO 
RESSONANCIA: HIPOINTENSO X HIPERINTENSO 

• CORONAL: COROA 
• SAGITAL: SIDE

DESCRIÇÃO DE RX DE TÓRAX COM PNEUMONIA BACTERIANA:
Consolidações pulmonares, Opacidades em vidro fosco, Derrame pleural, Infiltrados pulmonares, Área de consolidação arredondada ou oval.</pre>
            </div>
        </div>

    </div>

    <script>
        function showSection(id, btn) {
            document.querySelectorAll('.section').forEach(sec => sec.classList.remove('active'));
            document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            btn.classList.add('active');
        }

        function copyText(button) {
            const text = button.nextElementSibling.innerText;
            navigator.clipboard.writeText(text).then(() => {
                const oldText = button.innerText;
                button.innerText = 'Copiado!';
                button.style.background = 'var(--success)';
                setTimeout(() => {
                    button.innerText = oldText;
                    button.style.background = 'var(--accent)';
                }, 2000);
            });
        }
    </script>
</body>
</html>
