FROM alpine

RUN apk update && \
    apk upgrade && \
    apk add coreutils zsh zsh-vcs git && \
    zsh -c 'git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto" && \
    setopt EXTENDED_GLOB; \
    for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do \
      ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"; \
    done' && \
    sed -i s/'sorin'/'powerline'/ root/.zpreztorc

CMD ["zsh"]