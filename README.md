# chatbot-matfyz
Final project in subject machine learning on Matfyz faculty.

1. Po stiahnuti torrentu: https://mega.nz/#!ysBWXRqK!yPXLr25PgJi184pbJU3GtnqUY4wG7YvuPpxJjEmnb9AHo 
si ho niekde rozbalime, do kodu pridame cestu k rozbalenemu suboru. 
*POZOR* po rozbaleni bude mat 32GB.

2. Na otestovanie cesty mozme pouzit kod z tretej bunky v python notebooku, kde dosadime nasu cestu, ci je spravne zadana.

3. Ak je cesta validna, dosadime ju do prvej bunky do poslednej casti v kodu, with open(cesta...).

4. Spustime prvu bunku, vytvori sa nam databaza.

5. Potom spustime druhu bunku, ktora nam pripravy subory s testovacimi a trenovacimi datami.

TERAZ SA BUDEME DRZAT NAVODU Z NMT-CHATBOT githubu v casti SETUP: https://github.com/daniel-kukiela/nmt-chatbot
V kroku 7 nase trenovacie a testovacie data presunieme do foldru pod nazvom: new_data, a musia mat presne nazvy ako si ich vyzaduju, trenovacie premenujeme na train.to a train.from a testovacie na tst2012.to a tst2012.from. tst2013.to a tst2013.from budu nakopcene verzie roku 2012, len pod inym menom. parent je from, a comment je to.

Dat je v skutku vela, som to prehnal, preto som pouzil cloudovu sluzbu cez tento referal link, kde som dostal 10e na ucet co mi stacilo na natrenovanie: Paperspace GPUs in the cloud $10 referral link: https://goo.gl/sY3M7Y 

Hyperparametre sa nachadzaju v dir nmt-chatbot/setup/settings, kvoli dlzke trenovania som v dobe pisania reportu pouzil defaultne. Da sa vyhrat s vocab_size, 15k size potrebuje cca 4GB RAM, ale optimalne je 100k size.

hparams = {
    'attention': 'scaled_luong',
    'src': 'from',
    'tgt': 'to',
    'vocab_prefix': os.path.join(train_dir, "vocab"),
    'train_prefix': os.path.join(train_dir, "train"),
    'dev_prefix': os.path.join(train_dir, "tst2012"),
    'test_prefix': os.path.join(train_dir, "tst2013"),
    'out_dir': out_dir,
    'num_train_steps': 500000,
    'num_layers': 2,
    'num_units': 512,
    'optimizer': 'adam',
    'encoder_type': 'bi',
    'learning_rate':0.001,
    'beam_width': 10,
    'length_penalty_weight': 1.0,
    'num_translations_per_input': 10
    
}
