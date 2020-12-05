# Basic Arch install
At bootloader screen, add ``cow_spacesize=5G`` so the root filesystem is 5G
```
pacman -Syy && pacman -Syu
pacman -S ansible git
```

# Deploy
```ansible-playbook -i inventory.yaml site.yaml```
