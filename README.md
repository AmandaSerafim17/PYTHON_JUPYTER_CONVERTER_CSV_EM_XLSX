# Esse código foi usado em Jupyter para converter 1000 arquivos csv em xlsx

import pandas as pd
import os

def convert_csv_to_xlsx(directory):
    # Lista todos os arquivos no diretório
    files = os.listdir(directory)
    csv_files = [f for f in files if f.endswith('.csv')]

    # Loop através dos arquivos CSV e converte para XLSX
    for csv_file in csv_files:
        csv_path = os.path.join(directory, csv_file)
        xlsx_path = os.path.join(directory, csv_file.replace('.csv', '.xlsx'))
        
        # Lê o arquivo CSV
        df = pd.read_csv(csv_path)
        
        # Converte para XLSX
        df.to_excel(xlsx_path, index=False, engine='openpyxl')
        print(f'Convertido: {csv_file} -> {xlsx_path}')

# Define o diretório que contém os arquivos CSV
directory = r'Z:\Arquivo Pessoal - Equipe\Amanda\DIRETORIA_1'

# Chama a função de conversão
convert_csv_to_xlsx(directory)
