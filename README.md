# Убедитесь, что все предыдущие chia daemons остановлены
# Вы можете сделать это с помощью команды:
# ps aux | grep chia

# Загрузите новый исходный код Chia Node и установите его
git clone https://github.com/Chia-Network/chia-blockchain.git -b pools.testnet9 --recurse-submodules
cd chia-blockchain
sh install.sh
. ./activate

# Переключите на Mainnet 
export CHIA_ROOT=~/.chia/mainnet
chia init
chia configure --testnet false

# Запустите ноду и дождитесь синхронизации
# Если вы запускаете mainnet в первый раз, это может занять некоторое время
chia start farmer -r

# To connect to plot you need to have some coins on your wallet
# Open in browser https://faucet.chia.net 
# Enter your wallet to get some Chia coins for free - you will need them
# Для подключения к пулу вам нужно иметь немного монет на кошельке
# Откройте в браузере https://faucet.chia.net
# Укажите свой кошелек, чтобы получить несколько монет Chia бесплатно - они вам понадобятся

# После того, как у вас будет немного монет на кошельке - создайте plotnft с URL нашего пула
# Если вы из СНГ, подключитесь к ближайшему серверу по адресу https://cis.ecochia.io. Если нет - выберете ближайший к вам регион на сайте https://ecochia.io по кнопке Connect
chia plotnft create -u https://cis.ecochia.io -s pool

# Теперь вы можете создавать новые плоты и прикрепите их к нашему пулу
chia plots create -c <xch1ryuvwft4zwpjevksmlp264l9dv65hee5jrqh2arg8n43quhxspws22yhxm> ...... <YOUR PLOTING ARGS HERE>

# Перейдите на https://ecochia.io для присоединения к сообществу 14 тысяч человек, консоли фермы и chia explorer'a
# Скачайте Android приложение для получения уведолений о доходах и курсе XCH - 
