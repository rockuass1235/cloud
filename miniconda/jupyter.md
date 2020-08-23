# Jupyter 安裝

```
# 首先需要安裝Jupyter Notebook在base 環境
conda install jupyter

# 但是因為Anaconda(miniconda) 經常會根據項目的不同來建立不同的虛擬環境 我們當前只在默認的base環境下安裝了Jupyter Notebook,
# 如果要想Jupyter Notebook識別test 虛擬環境,那麼還需要在test 虛擬環境中安裝一下Jupyter Notebook 的kernel 包

conda activate test
conda install -n test ipykernel

# 注意:如果Jupyter Notebook還是無法顯示虛擬環境(主要是miniconda用戶)下的python,還需要在base環境下安裝nb_conda包

conda install nb_conda

```
