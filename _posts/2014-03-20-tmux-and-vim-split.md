---
layout: post
title: Tmux + Vim Split: Getting Together
tagline: apa apa aja
tags: [tmux, vim, vi]
---
{% include JB/setup %}

## Tmux + Vim Split

    ``` VimL
    # Smart pane switching with awareness of vim splits
    bind -n C-h run "(tmux display-message -p '#{pane_current_command}' | grep -iqE '(^|\/)vim(diff)?$' && tmux send-keys C-h) || tmux select-pane -L"
    bind -n C-j run "(tmux display-message -p '#{pane_current_command}' | grep -iqE '(^|\/)vim(diff)?$' && tmux send-keys C-j) || tmux select-pane -D"
    bind -n C-k run "(tmux display-message -p '#{pane_current_command}' | grep -iqE '(^|\/)vim(diff)?$' && tmux send-keys C-k) || tmux select-pane -U"
    bind -n C-l run "(tmux display-message -p '#{pane_current_command}' | grep -iqE '(^|\/)vim(diff)?$' && tmux send-keys C-l) || tmux select-pane -R"
    bind -n C-\ run "(tmux display-message -p '#{pane_current_command}' | grep -iqE '(^|\/)vim(diff)?$' && tmux send-keys 'C-\\') || tmux select-pane -l"
    ```

