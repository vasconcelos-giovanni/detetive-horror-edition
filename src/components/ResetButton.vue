<script setup>
import Cookies from 'js-cookie';

function resetGame() {
  alert('O jogo será reiniciado.');

  const allCookies = Cookies.get();
  Object.keys(allCookies).forEach((cookieName) => {
    Cookies.remove(cookieName);
  });

  window.location.reload(true);
}
</script>

<template>
  <div class="d-flex justify-content-center">
    <button class="btn btn-outline-danger" data-bs-toggle="modal" data-bs-target="#resetModal">
      Reiniciar jogo
    </button>
  </div>

  <!-- The Modal -->
  <div class="modal" id="resetModal">
    <div class="modal-dialog">
      <div class="modal-content">
        <!-- Modal Header -->
        <div class="modal-header">
          <h4 class="modal-title">Atenção!</h4>
          <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
        </div>

        <!-- Modal body -->
        <div class="modal-body">Deseja mesmo reiniciar o jogo?</div>

        <!-- Modal footer -->
        <div class="modal-footer">
          <button type="button" class="btn btn-outline-danger" @click="resetGame()">Sim</button>

          <button type="button" class="btn btn-outline-primary" data-bs-dismiss="modal">Não</button>
        </div>
      </div>
    </div>
  </div>
</template>
