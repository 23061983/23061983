#!/usr/bin/env python3
import argparse
from websherlock import scan_website
from profilesearch import search_username

def main():
    parser = argparse.ArgumentParser(description="WebSherlock: Ferramenta de pentest para varredura de sites e busca de perfis.")
    parser.add_argument("--url", help="URL do site para varredura de tecnologias (ex: https://example.com)")
    parser.add_argument("--username", help="Nome de usuário para busca em redes sociais")
    args = parser.parse_args()

    if args.url:
        print(f"[*] Iniciando varredura no site: {args.url}")
        scan_website(args.url)
    elif args.username:
        print(f"[*] Buscando perfis para o usuário: {args.username}")
        search_username(args.username)
    else:
        print("[!] Forneça uma URL (--url) ou um nome de usuário (--username).")
        parser.print_help()

if __name__ == "__main__":
    main()
