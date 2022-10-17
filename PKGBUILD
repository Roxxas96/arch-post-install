pkgname=arch-post-install
pkgver=0.1.0
pkgrel=1
pkgdesc='This is a post install package to download all most wanted applications for a DevOps'
url=http://example.com/
arch=('any')
license=('MIT')
source=(http://example.com/downloads/${pkgname}-${pkgver}.tar.gz)
sha256sums=('f0a90db8694fb34685ecd645d97d728b880a6c15c95e7d0700596028bd8bc0f9')

depends=(
    "git",
    "vim",
    "zsh",
    "visual-studio-code-bin",
    "docker",
    "docker-compose",
    "kubectl",
    "kubectx",
    "helm",
    "terraform",
    "rustup",
    "go",
    "gopls",
    "jdk-openjdk",
    "base-devel",
    "htop",
    "k9s",
    "minikube",
    "postman-bin",
    "dbeaver",
    "kio-gdrive",
    "google-chrome",
    "google-cloud-sdk",
    "aws-cli"
)

check() {
    git --version
    vim --version
    zsh --version
    code --version
    docker --version
    kubectl version
    kubectx --help
    helm version
    terraform version
    rustup --version
    go version
    gopls version
    java --version
    make --version #base-devel package
}

package() {
    echo "Installing oh-my-zsh"
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    echo "Installing power-level-10k"
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k & ZSH_THEME="powerlevel10k/powerlevel10k"
    echo "Installing zsh-autosuggestion"
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    echo "Installing zsh-syntax-highlight"
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    echo "Installing nvm"
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    echo "Thank you for using arch-post-install ! All packages are installed !"
    echo "We recomend you to download some fonts :"
    echo "MesloLGS NF for the terminal: https://github.com/romkatv/powerlevel10k#manual-font-installation"
    echo "Cascadia code for vscode: https://github.com/microsoft/cascadia-code/releases"
}
