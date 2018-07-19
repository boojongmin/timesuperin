# Timesuperin

Timesuperin �� '**Time Superin**tendent (�ð� ������)'�� ���Ӹ��ν� �ð迭 ������ �м� �� �̻� Ž���� ���� ���̺귯���Դϴ�.
�ð迭 ��ǥ�� �̺�Ʈ ������ Ʈ���带 ����Ͽ� ȸ�� ���� �����Ͽ� ���� ��ǥ�� ��ȭ�� �����ϰ�, �̷��� ������ ����� ũ�� ���̰� �߻��ϴ� �̻� ������ Ž���ϴ� ����� �����մϴ�. 

## ��ġ ���
timesuperin�� ����ϱ� ���ؼ� ���� �Ʒ� ���̺귯���� ��ġ�ؾ� �մϴ�.
* Rcpp
* rstan
* BH

�� ���̺귯���� ��ġ�� ���¿��� �Ʒ� �ڵ带 �����Ͻø� �˴ϴ�.

    devtools::install_github("ncsoft/timesuperin")

## ��� ���
�𵨸� �� �ð迭 �̻� Ž�� ����� �Ʒ��� �����ϴ�. 
���� timesuperin/resources �� �ִ� �����͸� �ҷ��ɴϴ�.

	setwd('./timesuperin/resources')
	train_data <- read.csv('./train_data.csv')
	test_data <- read.csv('./test_data.csv')

train_data.csv �� test_data.csv �� �� ���� �̺�Ʈ ������ ������ �޴� �ð迭 �������Դϴ�.
�𵨸��� ����� �н� �����ʹ� �Ʒ� �׸��� �����ϴ�. 

![](https://raw.githubusercontent.com/danbi-ncsoft/timesuperin/master/resources/train_data.png)

���� �� �����͸� �̿��� �Ʒ��� ���� �ð迭 ���� �����մϴ�.

	model <- model.timesuperin(train_data, model.type = 'lm', period = 6)

�� ���� �̿��� �׽�Ʈ �����Ϳ� �ִ� �̻� �����͸� Ž���ϱ� ���� �Ʒ��� ���� detect_anomal.timesuperin �Լ��� �����մϴ�.

	anomaly.detect <- detect_anomal.timesuperin(model, test_data, value = test_data$value)

�̻� Ž�� ����� ������ ���� Ȯ���� �� �ֽ��ϴ� (�� ���� �����Ͱ� upr�� lwr ������ ��� ���� Ȯ���� �� �ֽ��ϴ�).

	result$Interval_Plot

![](https://raw.githubusercontent.com/danbi-ncsoft/timesuperin/master/resources/anomaly_detect.png)
