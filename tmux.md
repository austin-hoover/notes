# tmux

## Create new session
```
tmux new -s mysession
tmux new-session -s mysession
```

## Create new session or attach to existing session
```
tmux new -A -s mysession
tmux new-session -A -s mysession
```

## Kill session
```
tmux kill-session -t mysession
```

## Show all sessions
```
tmux ls
tmux list-sessions
```

## Attach to session
```
tmux attach -t mysession
tmux attach-session -t mysession
```

## Rename session
```
Crtl+b $
```

## Detach from session
```
Ctrl+b d
```

