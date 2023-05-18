# sino
Why ?
#include<stdio.h>
#define lev 5;

int level(int max)
{
	int re = 0;
	do {
		printf("ポケモンのレベルを入力してください： {1---100}\n");
		scanf("%d", &max);
		switch (max) {
		case 0 : puts("正規である値を入力してください\n"); re++; break;
		default: puts("次の作業に移ります。\n"); break;
		}
	} while (re == 1);
	return max;
}
int kotaiti(int five)
{
	int re;
	do {
		printf("個体値を入力してください[ 1 -- 31 ]\n"); scanf("%d", &five);
		if (five < 1 || 31 < five)
			printf("間違えて入力していますよ\n");
		else
			("次の作業に移ります。\n");
	} while (five < 1 || 31 < five);
	return five;
}
int doryokuti(int fives)
{
	int re;
	do {
		printf("努力値を入力してください[ 0 -- 252 ]\n"); scanf("%d", &fives);
		if (fives < 0 || 252 < fives)
			printf("間違えて入力していますよ\n");
		else
			("次の作業に移ります。\n");
	} while (fives < 0 || 252 < fives);
	return fives;
}
int shininy(on)
{
	do {
		printf("色違いにしますか？[ Y...1 || N...0 ]\n"); scanf("%d", &on);
		on = on > 0 ? on : 0;
		switch (on) {
		case 0: puts("色違いにしません。\n"); break;
		case 1: puts("色違いにします。\n"); break;
		default: puts("やり直してください\n"); break;
		}
	} while (on < 0 || 1 < on);
	return on;
}
int waza(int f1[])
{
	int f = 0;
	printf("技を４個入力して下さい\n");
	for (int q = 0; q < 4; q++) {
		printf("技１："); scanf("%d", &f);
		switch (q) {
		case 0: f1[0] = f; break;
		case 1: f1[1] = f; break;
		case 2: f1[2] = f; break;
		case 3: f1[3] = f; break;
		default: puts("エラー\a\n"); break;
		}
	}
	printf("次の作業に移ります。\n");
	return f1[0], f1[1], f1[2], f1[3];
}
int size(int maxs)
{
	do {
		printf("ポケモンのサイズを入力してください： {0---999}\n"); scanf("%d", &maxs);
		if (maxs < 0 || 999 < maxs)
			printf("不当な値が入力されました。\n");
		else
			printf("次の作業に移ります。\n");
	} while (maxs < 0 || 999 < maxs);
	return maxs;
}
int akasi(int a)
{
	int h;
	do {
		do {
			printf("欲しい証を入力ししますか？　 [ Y...1 || N...0 ]\n"); scanf("%d", &h);
			if (h < 0 || 1 < h)
				printf("無効な値が入力されました。\a\n");
			else
				printf("次の作業に移ります。\n");
		} while (h < 0 || 1 < h);
			switch (h) {
			case 0: puts("終了します。\n"); break;
			case 1: puts("証を入力してください [ オール..1]\n"); scanf("%d", &a);
			}
	} while (h == 0);
}
int main(void)
{
	int Pokémon, boll, levels = 0, kotaitis[5], doryokutis[5], sum = 0, shininys, wazas[3], id, sizes, akasis , names , Re;
	printf("Pokémonの注文を作成します\n");
	printf("Pokémon名を入力して下さい\n"); scanf("%d", &Pokémon);
	printf("レベルを決めます。\n"); level(levels);
	printf("ボールを決めてください。\n");  scanf("%d", &boll);
	shininy(shininys);
	for (int n = 0; n < 6; n++) {
		switch (n) {
		case 0: puts("HPの個体値を入力してください\n");     kotaiti(kotaitis[0]); break;
		case 1: puts("攻撃力の個体値を入力してください\n"); kotaiti(kotaitis[1]); break;
		case 2: puts("防御力の個体値を入力してください\n"); kotaiti(kotaitis[2]); break;
		case 3: puts("特攻の個体値を入力してください\n");   kotaiti(kotaitis[3]); break;
		case 4: puts("特防の個体値を入力してください\n");   kotaiti(kotaitis[4]); break;
		case 5: puts("素早さの個体値を入力してください\n"); kotaiti(kotaitis[5]); break;
		default: puts("\a＊エラー\a\n");                                           break;
		}
	}
	do {
		for (int m = 0; m < 6; m++) {
			switch (m) {
			case 0: puts("HPの努力値を入力してください\n");     doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			case 1: puts("攻撃力の努力値を入力してください\n"); doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			case 2: puts("防御力の努力値を入力してください\n"); doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			case 3: puts("特攻の努力値を入力してください\n");   doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			case 4: puts("特防の努力値を入力してください\n");   doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			case 5: puts("素早さの努力値を入力してください\n"); doryokuti(doryokutis[m]); sum += doryokutis[m]; break;
			default: puts("\a＊エラー\a\n");                                           break;
			}
			if (510 < sum)
				printf("入力バファロー\a\n");
			else
				printf("次の作業に移ります。\n");
		}
	} while (510 < sum);
	printf("技を入力します。\n"); waza(wazas);
	do {
		do {
			printf("PokémonIDを入力してください[ Y...1 || ランダム...2\n"); scanf("%d", &id);
			if (id < 1 || 2 < id)
				printf("エラー\a\n");
			else
				printf("入力を開始します。\n");
		} while (id < 1 || 2 < id);
		if (1000000 < id || id < 0)
			printf("やり直してください\n");
		else
			printf("次の作業に移ります。\n");
	} while (1000000 < id || id < 0);
	if (id == 2)
		id = 000000;
	else
		printf("エラー\a\n");
	size(sizes);
	akasi(akasis);
	printf("プレイヤー名を入力してください：\n"); scanf("%d", &names);
	printf("Pokémon名：%d\n 色違い[%d]\n level：%d\n ボール：%d\n HPの個体値: %d\n 攻撃力の個体値:%d\n 防御力の個体値:%d\n 特攻の個体値:%d\n 特防の個体値:%d\n 素早さの個体値:%d\n HPの努力値:%d\n 攻撃力の努力値:%d\n 防御力の努力値:%d\n 特攻の努力値:%d\n 特防の努力値:%d\n 素早さの努力値:%d\n 技１：%d\n 技2:%d\n 技3:%d\n　技4:%d\n PokémonID:%d\n 証:%d\n サイズ:%d\n", Pokémon, shininys , levels, boll, kotaitis[0] , kotaitis[1] , kotaitis[2],
		kotaitis[3] , kotaitis[4] , kotaitis[5] , doryokutis[0] , doryokutis[1] , doryokutis[2] , doryokutis[3] , doryokutis[4] , doryokutis[5] , wazas[0] , wazas[1] , wazas[2] , wazas[3]  , id , akasis , sizes);
	printf("もう一体作りますか？ [ Y...1 || N...0 ]\a\n"); scanf("%d", &Re);
	if (Re == 0)
		printf("終わります。\n");
	else
		printf("もう一度やります。\n");
	return 0;

}
