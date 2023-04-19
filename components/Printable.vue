<template>
    <div>
        <button @click="printContent" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-md">
            Imprimer
        </button>
        <div id="printable" class="p-4 text-sm bg-white max-w-2xl mx-auto shadow-md break-words">
            <h1>
                Traitement de données à caractère personnel Information et consentement
                du patient
            </h1>
            <p>
                Madame, Monsieur,
            </p>
            <p>
                Votre professionnel de santé vous a proposé d’utiliser la plateforme
                CLINE pour qu’il puisse faciliter votre adressage, ou celui d’une
                personne dont vous êtes le représentant légal sur une étude clinique.
                Cela nécessite que votre professionnel de santé adresse des données à
                caractère personnel (ci-après “Données”) vous concernant ou concernant
                la personne dont vous êtes le représentant légal au professionnel chargé
                de la recherche clinique (étude ou essai clinique), incluant médecin
                investigateur et/ou attaché de recherche clinique habilité et/ou
                personnel de recherche clinique affilié à CLINE RESEARCH, qui décidera
                s’il peut vous inclure dans l’étude / essai clinique.
            </p>
            <p>
                Ce document a pour objet de vous informer sur le traitement, par votre
                professionnel de santé et par CLINE, des Données concernées, ainsi que
                de recueillir votre consentement à ce traitement. Votre professionnel de
                santé vous en fournira une copie afin que vous puissiez disposer à tout
                moment de ces informations.
            </p>
            <p>
                Vous être informé(e) que si vous ne souhaitez pas transmettre les
                Données demandées ou consentir à l’utilisation de CLINE, vous ne pourrez
                pas bénéficier de la solution CLINE.
            </p>
            <h2>Qui traite vos données ?</h2>
            <p>
                Le responsable du traitement de vos Données est votre professionnel de
                santé, à savoir :
            </p>
            <p>
                Nom du médecin adresseur : _________
                <br />
                Adresse du médecin adresseur : ___________
                <br />
                Téléphone du médecin adresseur : ___________
            </p>
            <p>
                CLINE ne traite vos données que sous son autorité et en vertu de ses
                instructions.
            </p>
            <h2>Quelle est la finalité de ce traitement ?</h2>
            <p>
                Le traitement de vos Données par CLINE a pour finalité d’adresser vos
                Données à des professionnels de la recherche clinique en vue de votre
                inclusion éventuelle sur une étude. La base légale de ce traitement est
                votre consentement tel qu’exprimé en bas de cette feuille. Si la
                personne concernée est un mineur de moins de quinze ans, il donne son
                consentement conjointement avec son représentant légal.
            </p>
            <h2>Qui accèdera à vos Données ?</h2>
            <p>
                Outre le personnel de CLINE et ses prestataires dans le strict cadre du
                fonctionnement de la solution CLINE, vos Données seront adressées à des professionnels de la recherche
                clinique qui disposent des compétences et de la capacité de vous inclure dans une étude clinique.
            </p>
            <h2>Combien de temps sont conservées vos Données ?</h2>
            <p>
                Vos Données sont conservées jusqu’à la fin de l’étude clinique si vous êtes inclue, et jusqu’à la décision
                de non inclusion si vous n’êtes pas inclus.
            </p>
            <h2>Quels sont vos droits et comment les exercer ?</h2>
            <p>
                Vous disposez des droits d’accès, de rectification, d’effacement, d’opposition, de limitation et de
                portabilité de vos données, ainsi que du droit de définir le sort de vos données personnelles après la mort.
                Vous pouvez en outre déposer une réclamation devant la CNIL.
            </p>
            <p>
                Enfin, vous pouvez retirer à tout moment votre consentement.
            </p>
            <p>
                Pour exercer ces droits, vous devez contacter le délégué à la protection des données (DPO) de CLINE RESEARCH
                par email à l’adresse suivante contact@cline-research.com, ou par courrier postale au 1 cours du Havre,
                75008 Paris.
            </p>
            <p>
                Pour plus de précisions, nous vous invitons à consulter la politique de confidentialité accessible sur le
                site www.cline-research.com.
            </p>
            <p>
                Je, _______________________, consens à ce que mes Données personnelles soient adressées par CLINE à des
                professionnels de santé afin qu’ils décident s’ils peuvent me prendre en charge.
            </p>
            <p>
                Fait à [VILLE], le [date et heure]
            </p>
            <div id="signature">
                <p>
                    Signature du patient
                </p>
                <p>
                    Ou signature du représentant légal
                </p>
            </div>
            <p id="indication">
                (si le patient a moins de 15 ans ou n'est pas en mesure de consentir)
            </p>
        </div>


    </div>
</template>
  
<script setup>
const printContent = () => {
    const printContentElement = document.getElementById("printable").outerHTML;
    const printWindow = window.open("", "_blank");
    printWindow.document.write(`
      <html>
        <head>
          <title>Imprimer</title>
          <style>
            @media print {
                @page { size: auto; margin: 0mm; }
                body { margin: 7mm; }
            }
            h1 {
                font-size: 1.5rem;
                text-align: center;
                font-weight: bold;
                margin-bottom: 0.5rem;
                margin-top: -0.5rem;
            }
            h2 {
                font-size: 1rem;
                margin-bottom: 0.5rem;
                margin-top: 0.5rem;
            }
            p {
                margin-bottom: 0.5rem;
                margin-top: 0;
            }
            #signature {
                display: flex;
                justify-content: space-between;
            }
            #indication {
                font-size: 0.8rem;
                margin-top: 0;
                text-align: right;
                margin-top: -0.5rem;
            }
          </style>
        </head>
        <body onload="window.print();window.close()">${printContentElement}</body>
      </html>
    `);
    printWindow.document.close();
};
</script>
  