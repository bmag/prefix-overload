# prefix-overload
Bind several commands to the same key (overloading). The correct
command is chosen by considering the prefix argument.

For example, this binds `ido-switch-buffer` and
`ido-switch-buffer-other-window` to `C-x b`:
```elisp
(define-prefix-overload switch-buffer-overload
    '(ido-switch-buffer ido-switch-buffer-other-window))
(define-key purpose-mode-map (kbd "C-x b")
    #'switch-buffer-overload)
```
To call `ido-switch-buffer`, press `C-x b`. To call
`ido-switch-buffer-other-window`, press `C-u C-x b`.
