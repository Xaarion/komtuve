<template>
    
                
                    <div class="card bg-light">
                        <div class="card-header">
                            <div class="form-inline">
                                <label>VM {{nombredevm}}</label>
                                <button class="btn x-square-fill ml-auto" type="button"></button>
                            </div>
                        </div>
                        <div class="card-body">
                            <div class="form-group">
                                <label for="inputName">Mémoire</label>
                                <div class="input-group mb-3">
                                    <input type="text" class="form-control" placeholder=""
                                        aria-label="Exemple de texte avec un bouton Addon" aria-describedby="button-addon1">
                                    <div class="input-group-prepend">
                                        <button class="btn trash-fill" type="button"></button>
                                    </div>
                                </div>
                            </div>
                            <div class="form-row">
                                <label for="inputEmail3">Nouveau Paramètre</label>
                                <select class="form-control" id="exampleFormControlSelect1">
                                    <option disabled>Mémoire</option>
                                    <option>Taille HDD</option>
                                    <option>Coeur</option>
                                    <option>Socket</option>
                                </select>
                            </div>
                        </div>
                    </div>
             

</template>

<script>

export default {
    name: "virtualMachina",
    props: {
        nombredevm: Number
        }
}

</script>
