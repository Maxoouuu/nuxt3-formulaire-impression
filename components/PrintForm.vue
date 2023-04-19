<template>
    <div>
        <button @click="openModal" class="bg-blue-500 text-white px-4 py-2 rounded">Remplir et imprimer le
            formulaire</button>
        <div v-show="isModalOpen" class="fixed inset-0 overflow-y-auto z-50">
            <div class="fixed inset-0 bg-black opacity-30" @click="closeModal"></div>
            <div class="min-h-screen px-4 text-center">
                <div
                    class="inline-block w-full max-w-md my-8 overflow-hidden text-left align-middle transition-all transform bg-white shadow-xl rounded-lg">
                    <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                        <div class="sm:flex sm:items-start">
                            <div class="mt-3 text-center sm:mt-0 sm:text-left">
                                <h3 class="text-lg leading-6 font-medium text-gray-900">Veuillez remplir les champs suivants
                                </h3>
                                <div class="mt-4">
                                    <label class="block text-sm font-medium text-gray-700">Nom du médecin adresseur</label>
                                    <input v-model="formData.doctorName" type="text"
                                        class="mt-1 focus:ring-blue-500 focus:border-blue-500 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md">
                                </div>
                                <div class="mt-4">
                                    <label class="block text-sm font-medium text-gray-700">Adresse du médecin
                                        adresseur</label>
                                    <input v-model="formData.doctorAddress" type="text"
                                        class="mt-1 focus:ring-blue-500 focus:border-blue-500 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md">
                                </div>
                                <div class="mt-4">
                                    <label class="block text sm font-medium text-gray-700">Téléphone du médecin
                                        adresseur</label>
                                    <input v-model="formData.doctorPhone" type="text"
                                        class="mt-1 focus:ring-blue-500 focus:border-blue-500 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md">
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="bg-gray-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
                        <button @click="printForm" type="button"
                            class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-4 py-2 bg-blue-500 text-base font-medium text-white hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 sm:ml-3 sm:w-auto sm:text-sm">
                            Imprimer
                        </button>
                        <button @click="closeModal" type="button"
                            class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 sm:mt-0 sm:w-auto sm:text-sm">
                            Annuler
                        </button>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>
<script setup>
import { ref } from 'vue'

const formData = ref({
    doctorName: '',
    doctorAddress: '',
    doctorPhone: ''
})

const isModalOpen = ref(false)

const openModal = () => {
    isModalOpen.value = true
}

const closeModal = () => {
    isModalOpen.value = false
}

const printForm = () => {
    // Insérer le contenu du formulaire dans le document
    const doc = new DOMParser().parseFromString(document.documentElement.innerHTML, 'text/html')
    doc.querySelector('.doctorName').textContent = formData.value.doctorName
    doc.querySelector('.doctorAddress').textContent = formData.value.doctorAddress
    doc.querySelector('.doctorPhone').textContent = formData.value.doctorPhone

    // Créer une iframe pour l'impression
    const iframe = document.createElement('iframe')
    iframe.style.display = 'none'
    document.body.appendChild(iframe)

    // Copier le contenu modifié dans l'iframe

    iframe.contentWindow.document.write(doc.querySelector('#printableForm').outerHTML)

    iframe.contentWindow.document.close()

    // Imprimer le contenu de l'iframe
    iframe.contentWindow.print()

    // Supprimer l'iframe après l'impression
    setTimeout(() => {
        document.body.removeChild(iframe)
    }, 200)
}
</script>
<style scoped>
/* Styles personnalisés ici */

</style>
  