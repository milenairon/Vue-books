<template>
    <header className="header">


        <div className="header__container container">
            <a href="/" className="header__logo link">
                <img src="../assets/images/icons/header-logo.svg" alt="Книги для олимпийцев" className="header__logo-icon" uk-svg />
            </a>

            <a href="#header__burger-menu" className="header__burger link" uk-toggle>
                <img src="../assets/images/icons/header-arrow.svg" alt="Стрелка" className="header__burger-icon" uk-svg />
            </a>

            <a href="#" className="header__basket link">
                <img src="../assets/images/icons/header-basket.svg" alt="Корзина" className="header__basket-icon" uk-svg />
            </a>
        </div>


        <div id="header__burger-menu" className="header__burger-menu" uk-open uk-modal-full uk-modal>
             <div className="header__burger-menu-content uk-modal-dialog uk-modal-body">
                <a href="#header__burger-menu" className="header__burger header__burger_active link" uk-toggle>
                    <img src="../assets/images/icons/header-arrow.svg" alt="Стрелка" className="header__burger-icon" uk-svg />
                </a>
            <ul className="header__burger-menu-items">
                    <li className="header__burger-menu-item"><a className="header__burger-menu-link link link_accent text text_m" href="/">Главная</a></li>
                    <li className="header__burger-menu-item"><a className="header__burger-menu-link link link_accent text text_m" href="/">Каталог</a></li>
                    <li className="header__burger-menu-item"><a className="header__burger-menu-link link link_accent text text_m" href="/">Корзина</a></li>
                </ul>
            </div>
        </div>


    </header>
</template>