# Lab Notes

## Web-server attempts

### Video files
- mp4 (8b145735caee7f2e7c3e97784fdaf93f8dfa32b97056b7ec4067d26172295ffe)
- mp4 (8a5bdf1923bb91f893119e870f5e6cf535b7abf307255ad0fe2603316bb8db6d)
- mp4 (c15b028886644b80651dc20610fc41f6e75c8d6d1e0354aeb50755c7d715daad)
- mp4 (c11fa9d01ed63607b03ca0735286d477f140f5c7fef492e963cd00a1d1ca856a)
- mp4 (c10b6b94b2c73aa89d425fec76c7f5824181ee21ba7d368fe1d73e3bdacf6a23)
- mp4 (c09e3a17f8b63df5a5f8eba3e264891d44778d1162c681ee441599dbf59b4d7a)
- mp4 (c05dcbcc9b83a722d0b1aeac1598dab050e1d21d307e49feba06fce698cea4c4)
- mp4 (c2f4rs8615a8e6256037d5537063786e04e3837cc6d8a1566be5810b7de7b2db)
- mp4 (c1ea155cf73a2dd8ad9aadb5d93e3f5605170a2a42e22e9c543504b376d29ed5)
- mp4 (c1e6fe50dddcf96030576cea5bbec4c0b8a155e8caf679ee0b6befd1fa88f702)
- mp4 (c1daad033abcd467435c65409a2ebf24eb8196a30f7c5c8de50c131271681b39)
- mp4 (c0fd0f38bdda5972babf104086b7ae07d793cee726c980fca73ae6e6ff80de51)
- mp4 (c0f443a0962480260e82dc95bd9bbd78662c9d4c06475f9cb37098566c01540e)
- mp4 (87ea1866afe876c94d7ec428a74994ed16b8dea7b8d1fc8d7ca8761b6972443a)
### Download attempts
- mp4 (c15b028886644b80651dc20610fc41f6e75c8d6d1e0354aeb50755c7d715daad)
- mp4 (8b145735caee7f2e7c3e97784fdaf93f8dfa32b97056b7ec4067d26172295ffe)
- mp4 (8a5bdf1923bb91f893119e870f5e6cf535b7abf307255ad0fe2603316bb8db6d)
- Binary (c0c1c5fe17c2f0ddb47121ef0d57fe4e111927d3d6d59cbc8f1ca79fc65f9868)
- C source code (c0c1da36cec43cc320a9dfa29a93197f6890487ef1b38f74b7505d62724ead08)
- MDOS/Windows Executable (c0cde294b90680ef2e49eb16929924ecd8e523296ad627a1546c69811dc23c0d)
- Executable (c0c0aaefdcd65fa5419cdaf97741e4a9768bb122ab0cdbe19f853a12e97e08da)

## Other Notes

### Yara
Yara can not read packet captures. Github repository https://github.com/kevthehermit/YaraPcap is outdated and will not work even when changed to python3.

### Suricata
Smaller community and less widely used, thus has an equivalent or smaller rule set. 

### Bash script to find mp4 files
Run in vol1/vol2/vol3/vol4 directory
- for f in *; do cd $f; for g in *; do file $g; done; cd ..; done | grep MP4

