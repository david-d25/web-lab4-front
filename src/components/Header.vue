<template>
  <header class="header_wr -bg-dark -color-light">
    <container>
      <div class="header">
        <router-link to="/" class="desktop_menu__logo -color-light" physical-body physical-body-bg="#2b2b2b">{{ $t('components.header.title') }}</router-link>
        <span class="header__text" physical-body physical-body-bg="#2b2b2b">{{ $t('components.header.student_info') }}</span>
        <language-selector physical-body physical-body-bg="#2b2b2b"/>
        <user-dropdown :user="$parent.user" physical-body physical-body-bg="#2b2b2b"/>
      </div>
    </container>
  </header>
</template>

<script>
  import Container from "#/components/Container";
  import LanguageSelector from "#/components/LanguageSelector";
  import UserDropdown from "#/components/UserDropdown";

  export default {
    components: {UserDropdown, LanguageSelector, Container },
  }
</script>

<style scoped lang="scss">
  @import "~$src/styles/tablet.scss";

  .desktop_menu__logo {
    display: flex;
    align-items: center;
    flex: 1;
  }

  .header__text {
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 3;
    color: rgba(255, 255, 255, .5);
    font-size: .65em;

    @include tablet {
      display: none;
    }
  }

  .header_wr {
    position: absolute;
    z-index: 999;
    width: 100%;
    top: 0;
    left: 0;
  }

  .header {
    font-size: 24px;
    display: flex;
    height: 50px;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    transition: 300ms;
    user-select: none;
    opacity: 1;
  }

  .header_wr.hidden .header {
    opacity: 1;
  }

  .header__title {
    display: none;
    align-items: center;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    padding: 10px 0 10px 10px;
    flex: 4;
  }
</style>
