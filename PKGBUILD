pkgname=arch-post-install
pkgver=0.1.0
pkgrel=1
pkgdesc='This is a post install package to download all most wanted applications for a DevOps'
arch=('x86_64')
url="https://github.com/Roxxas96/arch-post-install"
license=('MIT')
depends=('git' 'vim' 'zsh' 'visual-studio-code-bin' 'docker' 'kubectl' 'kubectx' 'helm' 'terraform' 'rustup' 'go' 'gopls' 'jdk-openjdk')
makedepends=('git')
source=('arch-post-install::git://github.com/Roxxas96/arch-post-install.git')
md5sums=('SKIP')

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

pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "$pkgname"
    echo "Build complete"
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
