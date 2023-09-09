# GameController 2023

## Como compilar

### Pré-requisitos

- Rust e outras dependências tauri (só seguir o tutorial desse link)(https://tauri.app/v1/guides/getting-started/prerequisites)
- nodejs e npm 
	- usar a versão do nodejs acima da v14 (eu utilizei a v18.17.1)
	- se tiver dificuldade em atualizar o nodejs siga esse [tutorial] (https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-22-04)
- libclang (for bindgen)
	- No Linux
	```bash
	sudo apt update
	sudo apt install llvm
	```
	- Configurar a variável de ambiente 'LIBCLANG_PATH', lembre de substituir  <versão> pela versão específica do LLVM que você instalou:
	```bash
	nano ~/.bashrc
	export LIBCLANG_PATH=/usr/lib/llvm-<versão>/lib
	```
- clang
```bash
sudo apt install clang
```

### Comandos

- Compilar o frontend:
```bash
cd frontend
npm ci
npm run build
```

- Compilar o código Rust com 'cargo': 
```bash
cargo clean
cargo build
```


### Dev

- instalar o tauri CLI 
```bash
cargo install tauri-cli
```

- Front end e back end no modo dev:
```bash
cargo tauri dev
```

### Executando o GameController
- Precisa estar no diretório 'game_controller_app' pois é onde está o binário 
```bash
cd game_controller_app
cargo run
```

se desejar executar em modo de liberação (mais otimizado) utilizar:
```bash
cargo run --release
```