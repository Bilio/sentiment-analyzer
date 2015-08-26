# Sentimental Analysis ���ϱ������R

## Environment

* Eclipse Java EE

* JDK/JRE v1.8

* UTF-8 File Encoding


## Process

![Process](http://i.imgur.com/P3BaNOF.jpg)

	���F�즳���~�������r��]���B�ϡB�{�׵��^�A�Q��Training��X��L�S�O�����ϵ��J

	����A�ھڥy���u���ϵ��J�v�X�{���ƶq�A�f�t�[���y�𪺵{�׵��A���w�@���ơA�@�����_�з�


## Frame Work

![FrameWork](http://i.imgur.com/NuJmxNB.jpg)

* HashMap (Key, Value) = (������, ��/��)

* �i�H�bO(1)���ɶ����P�_����O�_�㦳�S�w����


## Details about Training

Step1 �μ��I�B�����_�y

	���Ѽ��I�Ÿ��_�y�A�èϥ�Open Source��Library�]�����_���t�Ρ^

	�ϥ�Trie���c��B�ʺA�W����{�̨Τ���
	
	Reference: https://github.com/huaban/jieba-analysis

Step2 �p��U����X�{���ơ]�W�v�^

	�o��H�u���v����쪺��ƫ�A�p����Training Data���A�U����X�{���r�ơ]�W�v�^

Step3 ��ܤ@�Ǧb�����峹���A��N��ʪ����t�����J�A�[�J�r��

	��ܪ��зǡGSO�� > 3.0�A�[�JPositive�r��FSO�� < -3.0�A�[�JNegative�r��

![PMISO](http://i.imgur.com/PU2UCXj.jpg)


## Details about Analyzing

Step1 �_�y

	�H���I�B�U���Ÿ��_�y�]���H�����_�y�A�]���@������@�h���שΦ^�С^

Step2 ��{�׵�

	�N�@�ӥy�l�������p�����A�P�_�I�_�᪺���J�O�_�ݩ�Dictionary�����{�׵�

	�p�G�O�A�h�N�ӥy�l�����ƭ��v���H2

		Example

		�u�o�a���]����A�ȫD�`�t�l�v�|����

		�u�a���]����A�ȫD�`�t�l�v�B�u�o�a���]����A�ȫD�`�t�v�K�u�`�t�v�B�u�D�`�v�K�u�o�v

		�Ѫ���u�B�᩹�e���I�r�覡�]�קK��������r�S�����A�Ϧӧ��u���^

		���{�׵�����r��A�|�N���v��2�A�ç�������q�y�l���R��

Step3 �䥿�ϭ������ε�

	�I�r�B�R�r�覡�P�W�@�B�A�u�O��I�_�᪺���J���hPositive�BNegative Dictionary�����

	����A�p�G�O�������J�A����+1�A�t���h-1�]�f�t�{�׵������v�A�i���ܬ���2�^

Step4 ��XShifter�]���B�S�^

	���y�l���Ѿl���r�J�A�O�_�]�t�u���v�Ρu�S�v

	�p�G���A�h�N�ӥy�l�����ƭ��W-1

Step5 �P�_��h���ת����϶ɦV

	��h���ת�����=�U�y�l�����ƥ[�`�A�Y���פ��� �� 0�A�P�������ɦV�A�Ϥ��t��


## API

* Source Code�w���]��`SentimentalAnalysis.jar`�A�~�[`jieba-analysis.jar`

* Library Setting�n����A�ϥ�`SentimentAnalyzer()`�غc�l�Mmethod��`work()`��run

* static method��`setNTHREADS(int)` �i�]�wTraining�MAnalyzing�ɪ�Threads�ƶq

* static method��`setSORate(double)` �i�վ�Training�ɨ��r���Y�Ե{��

* static method - `setDictionary(String, String, String)` �i�ۭq�����r�媺���|�P�ɦW

* static method - `setTrainingData(String, String)` �i�ۭqTraining��ƪ����|�P�ɦW

![API](http://i.imgur.com/hIH7vqM.jpg)


## Input File Format

* Training�Ϊ���r��

	�w�]��`docs/training.txt`

	�@�h���ץe�@��A���[�s���]�Y�L�A���إߪ��ɮס^

* Training������

	�w�]��`docs/answer.txt`

	��ƻPtraining.txt�ۦP�A�@��@�r�A�H�b�Τj�gP/N�Ӫ�ܡ]�Y�L�A���إߪ��ɮס^

* ���B�ϡB�{�צr��

	�w�]��`docs/positive.txt`, `docs/negative.txt`, `docs/adv.txt`

	�@�ӳ���]��r�^�e�@��A���[�s��

* �����R������

	�w�]��`docs/opinion.txt`

	�榡�PTraining���ɮ׬ۦP�A�@�h���ץe�@��A���[�s��


## Output File Format

* ���R��|���e�ؿ�����`result.txt`

* �w�]��`result.txt`�A�C�h���ת����R�e4��

* �Ĥ@�欰���R���G�A�ĤG������_���A�ĤT��h�O��쪺����r�A�̫�@��ť�

* �ɧ��h�|�t�C�������R���A���ϵ��פ����e10�W����r

