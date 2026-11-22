# Apex Agency

Site institucional estático da Apex Agency.

## Arquitetura

O projeto usa HTML, CSS e JavaScript tradicionais, mantidos em uma única página. O Vite é utilizado apenas como servidor de desenvolvimento e ferramenta de build.

Apenas o Tailwind CDN deve ser substituído por uma compilação local em uma etapa futura, caso o projeto evolua.

## Pré-requisitos

- Node.js 20+
- npm

## Instalação

```powershell
npm install
```

## Desenvolvimento

```powershell
npm run dev
```

O servidor local é exibido pelo terminal.

## Build de produção

```powershell
npm run build
```

Os arquivos finais são gerados na pasta `dist/`.

## Pré-visualização da build

```powershell
npm run preview
```

## Arquivos principais

- `index.html`: versão preparada para execução pelo Vite.
- `apex_agency_make_your_mark.html`: arquivo HTML original preservado.
- `apex_agency_make_your_mark.original.html`: cópia de segurança criada durante a preparação técnica.
