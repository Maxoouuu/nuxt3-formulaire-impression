<template>
    <div id="printableForm" class="">
        <h3>Traitement de données à caractère personnel Information et consentement du patient
        </h3>

        <p>Madame, Monsieur,</p>

        <p>
            Votre professionnel de santé vous a proposé d’utiliser la plateforme CLINE pour qu’il puisse faciliter votre
            adressage, ou celui d’une personne dont vous êtes le représentant légal sur une étude clinique. Cela nécessite
            que
            votre professionnel de santé adresse des données à caractère personnel (ci-après “Données”) vous concernant ou
            concernant la personne dont vous êtes le représentant légal au professionnel chargé de la recherche clinique
            (étude
            ou essai clinique), incluant médecin investigateur et/ou attaché de recherche clinique habilité et/ou personnel
            de
            recherche clinique affilié à CLINE RESEARCH, qui décidera s’il peut vous inclure dans l’étude / essai clinique.
        </p>

        <p>
            Ce document a pour objet de vous informer sur le traitement, par votre professionnel de santé et par CLINE, des
            Données concernées, ainsi que de recueillir votre consentement à ce traitement. Votre professionnel de santé
            vous en
            fournira une copie afin que vous puissiez disposer à tout moment de ces informations.
        </p>

        <p>
            Vous être informé(e) que si vous ne souhaitez pas transmettre les Données demandées ou consentir à l’utilisation
            de
            CLINE, vous ne pourrez pas bénéficier de la solution CLINE.
        </p>

        <h3>Qui traite vos données ?</h3>
        <p>
            Le responsable du traitement de vos Données est votre professionnel de santé, à savoir : 
            <span class="doctorName">Nom du médecin adresseur :</span>
            <span class="doctorAddress">Adresse du médecin adresseur :</span>
            <span class="doctorPhone">Téléphone du médecin adresseur :</span>
        </p>

        <p>
            CLINE ne traite vos données que sous son autorité et en vertu de ses instructions.
        </p>

        <h3>Quelle est la finalité de ce traitement ?</h3>

        <p>
            Le traitement de vos Données par CLINE a pour finalité d’adresser vos Données à des professionnels de la
            recherche
            clinique en vue de votre inclusion éventuelle sur une étude. La base légale de ce traitement est votre
            consentement
            tel qu’exprimé en bas de cette feuille. Si la personne concernée est un mineur de moins de quinze ans, il donne
            son
            consentement conjointement avec son représentant légal.
        </p>

        <h3>Qui accèdera à vos Données ?</h3>

        <p>
            Outre le personnel de CLINE et ses prestataires dans le strict cadre du fonctionnement de la solution CLINE, vos
            Données seront adressées à des professionnels de la recherche clinique qui disposent des compétences et de la
            capacité de vous inclure dans une étude clinique.
        </p>

        <h3>Combien de temps sont conservées vos Données ?</h3>

        <p>
            Vos Données sont conservées jusqu’à la fin de l’étude clinique si vous êtes inclue, et jusqu’à la décision de
            non
            inclusion si vous n’êtes pas inclus.
        </p>

        <h3>Quels sont vos droits et comment les exercer ?</h3>

        <p>
            Vous disposez des droits d’accès, de rectification, d’effacement, d’opposition, de limitation et de portabilité
            de
            vos données, ainsi que du droit de définir le sort de vos données personnelles après la mort. Vous pouvez en
            outre
            déposer une réclamation devant la CNIL.
        </p>

        <p>
            Enfin, vous pouvez retirer à tout moment votre consentement.
        </p>

        <p>
            Pour exercer ces droits, vous devez contacter le délégué à la protection des données (DPO) de CLINE RESEARCH par
            email à l’adresse suivante contact@cline-research.com, ou par courrier postale au 1 cours du Havre, 73008 Paris.
        </p>

        <p>
            Pour plus de précisions, nous vous invitons à consulter la politique de confidentialité accessible sur le site
            www.cline-research.com.
        </p>

        <p>
            Je, , consens à ce que mes Données personnelles soient adressées par CLINE à des professionnels de santé afin
            qu’ils
            décident s’ils peuvent me prendre en charge.
        </p>

        <p>
            Fait à [VILLE], le [date et heure]
        </p>

        <p>
            Signature du patient Ou signature du représentant légal
        </p>

        <p>
            (si le patient a moins de 13 ans ou n'est pas en mesure de consentir)
        </p>

    </div>
</template>
  
<style scoped>
h3 {
    font-size: 1.3em;
    font-weight: bold;
    margin: 1em 0;
    line-height: 1em;
}
 /* Ajuster la taille et la position du contenu imprimé */
 #printableForm {
        width: 100%;
        max-width: 210mm;
        margin: 0 auto;
        box-sizing: border-box;
    }

p {
    line-height: 1.5em;
}

@media print {
    @page {
        size: A4;
        margin: 20mm;
    }

    body {
        font-size: 12px;
        line-height: 1;
    }

    p {
        margin: 0;
        line-height: 1;
        margin-top: -50px;
    }

    h3 {
        font-size: 1rem;
        margin: -50;
    }
}

</style>