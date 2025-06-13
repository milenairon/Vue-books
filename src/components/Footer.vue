<template>
    <footer className="footer">
        <div className="footer__container container">

            <div className="footer__box">
                <a href="/" className="footer__logo link">
                    <img src="../assets/images/icons/logo.svg" alt="Книги для олимпийцев" className="footer__logo-icon" uk-svg />
                </a>

                <a href="tel:+30922040281" className="footer__logo link text color-accent">+30922040281</a>
            </div>


            <nav className="footer__nav">
              <ul className="footer__nav-items">
                    <li className="footer__nav-item"><a className="footer__nav-link link text" href="/">Главная</a></li>
                    <li className="footer__nav-item"><a className="footer__nav-link link text" href="/">Каталог</a></li>
                    <li className="footer__nav-item"><a className="footer__nav-link link text" href="/">Корзина</a></li>
                </ul> 
            </nav>

        </div>
    </footer>
</template>
<style>
.footer {
    background-color: #1596C1;
}

.footer__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    padding-top: 15px;
    padding-bottom: 15px;
}

.footer__box {

}

.footer__logo {
    flex: 0 0 auto;
    margin-right: 6rem;
}

@media (any-hover: hover) {
    .footer__logo:hover svg path {
        fill: #000;
        transition: 0.3s;
    }
}

.footer__logo-icon {
    height: 80px;
}

.footer__nav {}

.footer__nav-items {
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 40px;
}

.footer__nav-item {}

.footer__nav-link {}
</style>