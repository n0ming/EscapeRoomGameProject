#include <stdio.h>
#include <stdlib.h>
#include <Windows.h>
#pragma once
#include "Positions.h"

#define WIDTH 30        //가로
#define HEIGHT 40        //세로
#define TRUE 1
#define FALSE 0

Enemy enemy[WIDTH];
Player player;
void finish();
void twostage();
void brandpicture();
void init();    // 초기값
void CreateEnemy();     // 적 생성 
void FallEnemy();   // 적의 움직임
void DelEnemy();    // 피하기 성공한 적(바닥에 떨어진 적) 삭제 
int DamagedPlayer();    // 플레이어가 적에게 닿을 경우 (패배) 
int isKeyDown(int key);     // 키 다운 처리 
void MovePlayer();      // 플레이어 이동 (좌/우) 
void PrintGame();     // 게임 화면 출력
void finish();      // 열쇠에 닿을경우 해당 스테이지 클리어 및 다음스테이지 갈지에 대한 여부 화면 출력
void twostage();    // 2 스테이지로 이동
void brandpicture();    // 방탈출 로고
void startpicture();
void titleDraw();
void menuDraw();
void secondgamemiro(); // 2스테이지 미로출력
void PrintGame2();
void MovePlayer2();

void startpicture()
{
    brandpicture();
    for (int i = 0; i < 10; i++) {
        system("color 09");
        Sleep(100);
        system("color 06");
    }
    printf("\n\n\n");
    printf("                          ┌──────────────────────────────────────────────┐\n");

    printf("                          │                                              │\n");

    printf("                          │                 < 방탈출 게임 >              │\n");
    printf("                          │                                              │\n");
    printf("                          │               열쇠에 접근하세요!             │\n");
    printf("                          │                                              │\n");
    printf("                          │                 자동으로 시작!               │\n");
    printf("                          │                                              │\n");
    printf("                          │      게임 조작키 : 방향키 ←, ↑, ↓, →     │\n");
    printf("                          │                                              │\n");
    printf("                          ├──────────────────────────────────────────────┤\n");
    printf("                          │                                              │\n");
    printf("                          │                                              │\n");
    printf("                          │                              ▩▩            │\n");
    printf("                          │                ♥==          ▩              │\n");
    printf("                          │                              ▩▩            │\n");
    printf("                          │        ♥==                  ▩              │\n");
    printf("                          │           ○        ♥==     ▩▩▩          │\n");
    printf("                          │          ┌□┘                ▩  ▩          │\n");
    printf("                          │      ...  ll      ♥==       ▩▩▩          │ \n");
    printf("                          │                                              │\n");
    printf("                          │                                              │\n");
    printf("                          └──────────────────────────────────────────────┘\n");
    Sleep(5000);
 
}
//// 초기값 ////
void init()
{
    int i;
    for (i = 0; i < WIDTH; i++)
        enemy[i].con = FALSE;
    //플레이어 위치는 중앙
    player.x = WIDTH / 2;
    player.y = HEIGHT; //개입
}

//// 피할 적들 처리 ////
/* 적 생성 */
void CreateEnemy()
{
    int i;

    for (i = 0; i < WIDTH; i++)
    {
        //해당 인덱스[i]에 적이 없으면 (FALSE 이면 실행)
        if (!enemy[i].con)
        {
            //가로 (x축) 무작위로 적 출현, 세로(y축)은 출현 위치 항상 일치
            enemy[i].x = rand() % WIDTH;
            enemy[i].y = HEIGHT - 1;
            //적이 출현한 인덱스 [i]의 상태 = TRUE로 변경
            enemy[i].con = TRUE;
            return;
        }
    }
}
/* 적의 움직임 */
void FallEnemy()
{
    int i;
    for (i = 0; i < WIDTH; i++)
    {
        //해당 인덱스 [i]에 적이 있으면 (TRUE라면) 움직임 실행
        if (enemy[i].con)
        {
            enemy[i].y--;
        }
    }
}
/* 피하기 성공한 적(바닥에 떨어진 적) 삭제 */
void DelEnemy()
{
    int i;
    for (i = 0; i < WIDTH; i++)
    {
        if (enemy[i].con && enemy[i].y < 0)
            enemy[i].con = FALSE;
    }
}
/* 플레이어가 적에게 닿을 경우 (패배) 또는 열쇠에 닿을 경우 다음스테이지 통과 */
int DamagedPlayer()
{
    int i;
    for (i = 0; i < WIDTH; i++)
    {
        //적의 상태가 TRUE && 적의 위치가 y=0 즉 바닥 && 적의 x축 위치 = 플레이어의 x축 위치
        if ((enemy[i].con && enemy[i].y == 0) && (enemy[i].x == player.x))
            return TRUE;
        else if (player.x == WIDTH / 2 - 1 && player.y == HEIGHT / 2 - 9)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2  && player.y == HEIGHT / 2 +1-8)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 - 1 && player.y == HEIGHT / 2 - 8)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 - 1 && player.y == HEIGHT / 2 - 7)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 7)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 6)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 5)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 4)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 && player.y == HEIGHT / 2 - 4)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 3)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 + 1 && player.y == HEIGHT / 2 - 2)
        {
            finish();
            return TRUE;
        }
        else if (player.x == WIDTH / 2 && player.y == HEIGHT / 2 - 2)
        {
            finish();
            return TRUE;
        }
    }
    //닿지 않았으면 FALSE 반환
    return FALSE;
}

//// 플레이어 처리 ////
/* 키 다운 처리 */
int isKeyDown(int key)
{
    //***GetAsyncKey는 키가 눌렸다면 최상위 비트를 1로 설정, 이전에 키가 눌렸다면 최하위 비트를 1로 설정
    //0x8000은 최상위 비트 -> 16진수는 2비트가 4개 모인 비트 -> 0x8000 = 1000 0000 0000 0000를 의미
    // 즉 최하위 비트는 0x0001 -> 0000 0000 0000 0001
    // 따라서 (GetAsyncKeyState(key) & 0x8000) != 0 은 현재 키가 눌려있다면 참(TRUE)
    return ((GetAsyncKeyState(key) & 0x8000) != 0);
}

/* 플레이어 이동 (좌/우) */
void MovePlayer()
{
    if (isKeyDown(VK_LEFT))
        player.x--;
    if (isKeyDown(VK_RIGHT))
        player.x++;
    if (isKeyDown(VK_UP))
        player.y--;
    if (isKeyDown(VK_DOWN))
        player.y++;

    //위치 범위 제한
    if (player.x < 0)
        player.x = 0;
    if (player.x > WIDTH - 1)
        player.x = WIDTH - 1;
    if (player.y > HEIGHT+1)
        player.y = HEIGHT;
    if (player.y < 0)
        player.y = 0;


}

//// 게임 화면 출력 ////
void PrintGame()
{
    //모든 화면 clear
    system("cls");

    int i;
    for (i = 0; i < WIDTH; i++)
    {
        if (enemy[i].con)
        {
            //적 위치에 적군 출력
            gotoxy(enemy[i].x, HEIGHT - enemy[i].y);
            printf("♥");
        }
    }
    //플레이어 출력
    gotoxy(player.x, player.y);
    printf("□");

    gotoxy(0, HEIGHT + 1);
    for (i = 0; i < WIDTH; i++)
        printf("▩");
    gotoxy(0, 0);
    for (i = 0; i < WIDTH; i++)
        printf("▩");
    gotoxy(0, 0);
    for (i = 0; i < HEIGHT+1; i++)
    {
        printf("▩\n");
    }

    for (i = 0; i < HEIGHT + 2; i++)
    {
        gotoxy(WIDTH, i);
        printf("▩\n");
    }


    gotoxy(WIDTH / 2, HEIGHT / 2-9);
    printf("▩");
    gotoxy(WIDTH / 2+1, HEIGHT / 2 - 9);
    printf("▩");
    gotoxy(WIDTH / 2-1, HEIGHT / 2 -9);
    printf("▩");
    gotoxy(WIDTH / 2, HEIGHT / 2 + 1-8);
    printf("▩");
    gotoxy(WIDTH / 2-1, HEIGHT / 2-8);
    printf("▩");
    gotoxy(WIDTH / 2 - 1, HEIGHT / 2+1-8);
    printf("▩");
    gotoxy(WIDTH / 2 +1, HEIGHT / 2-8);
    printf("▩");
    gotoxy(WIDTH / 2 +1, HEIGHT / 2 + 1-8);
    printf("▩");
    gotoxy(WIDTH / 2 + 1, HEIGHT / 2 + 2-8);
    printf("▩");
    gotoxy(WIDTH / 2 + 1, HEIGHT / 2 + 3-8);
    printf("▩");
    gotoxy(WIDTH / 2 + 1, HEIGHT / 2 + 4-8);
    printf("▩");
    gotoxy(WIDTH / 2, HEIGHT / 2 + 4-8);
    printf("▩");
    gotoxy(WIDTH / 2 + 1, HEIGHT / 2 + 5-8);
    printf("▩");
    gotoxy(WIDTH / 2 + 1, HEIGHT / 2 + 6-8);
    printf("▩");
    gotoxy(WIDTH / 2, HEIGHT / 2 + 6-8);
    printf("▩");

    gotoxy(WIDTH +10, HEIGHT / 2 -11);
    printf("방탈출 1STAGE");
    gotoxy(WIDTH + 9, HEIGHT / 2 - 10);
    printf("=================");
    gotoxy(WIDTH + 9, HEIGHT / 2 - 12);
    printf("=================");
    gotoxy(WIDTH + 9, HEIGHT / 2 - 10);
    printf("=");
    gotoxy(WIDTH + 9, HEIGHT / 2 - 11);
    printf("=");
    gotoxy(WIDTH + 9, HEIGHT / 2 - 12);
    printf("=");
    gotoxy(WIDTH + 17, HEIGHT / 2 - 11);
    printf("=");
    gotoxy(WIDTH + 5, HEIGHT / 2 - 9);
    printf("= = = = = = = = = = = = = = = = = ");
    for (i = 0; i < 13; i++)
    {
        gotoxy(WIDTH + 5, HEIGHT / 2 - 8 + i);
        printf("=");
    }
    gotoxy(WIDTH + 5+1, HEIGHT / 2 + 9);
    printf("- - - - - - - - - - - - - - - - ");
    gotoxy(WIDTH + 5, HEIGHT / 2 - 9 + 12);
    printf("= = = = = = = = = = = = = = = = =");
    for (i = 0; i < 13; i++)
    {
        gotoxy(WIDTH + 22, HEIGHT / 2 - 9 + i);
        printf("=");
    }
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 2);
    printf("       < 탈출 방법 > ");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 +4);
    printf(" 위에서 떨어지는 장애물을 ");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 5);
    printf("피해서 방을 탈출할 수 있는");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 6);
    printf("      열쇠를 먹어라!");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 9);
    printf("중앙에 있는 열쇠에 도달하면");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 10);
    printf("  열쇠를 먹을 수 있습니다");
    gotoxy(WIDTH + 5, HEIGHT / 2 - 9 + 13);
    printf("- - - - - - - - - - - - - - - - - -");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 15);
    printf("          < 주의 >");
    gotoxy(WIDTH + 7, HEIGHT / 2 - 9 + 16);
    printf("   목숨은 단 '한'번입니다");
    for (i = 0; i < 5; i++)
    {
        gotoxy(WIDTH + 5, HEIGHT / 2+5 + i);
        printf("-");
    }
    for (i = 0; i < 5; i++)
    {
        gotoxy(WIDTH + 22, HEIGHT / 2 + 5 + i);
        printf("-");
    }
}

void finish()
{
    system("cls");
    int next;
    printf("\n");
    printf("\n");
    printf("\n");
    brandpicture();
    printf("\n\n\n");
        printf("                ========================================================================");  
        gotoxy(WIDTH / 2-6, HEIGHT / 2 + 3);
        printf("1 STAGE 방탈출에 성공하셨습니다. 다음 2STAGE 방탈출로 넘어가겠습니까?");
        gotoxy(WIDTH/2 + 7, HEIGHT / 2 + 6);
        printf("[ YES(y) / NO(n) ]");
        gotoxy(WIDTH/2 + 6, HEIGHT / 2 + 7);
        printf("(y 또는 n을 눌러주세요)\n");
        gotoxy(WIDTH / 2 - 7, HEIGHT / 2 + 9);
        printf("========================================================================");
        for (int i = 0; i < 9; i++)
        {
            gotoxy(WIDTH / 2 - 7, HEIGHT / 2 + 9 - i);
            printf("=");
        }
        for (int i = 0; i < 9; i++)
        {
            gotoxy(WIDTH / 2 - 7 + 36, HEIGHT / 2 + 9 - i);
            printf("=");
        }
        next = getchar();
        if (next == 'y')
        {
            twostage();
        }
        else
           exit(0);
}

void twostage()
{
    system("cls");
    printf("두번째 스테이지 시작");
    titleDraw();
    menuDraw();
    system("cls");
    system("mode con cols=200 lines=100 | title 게임제목 ");
    do {
        srand((int)malloc(NULL));
        MovePlayer2();
        PrintGame2();
        Sleep(100);
    //플레이어 출력
    } while (1);
}
void PrintGame2()
{
    //모든 화면 clear
    system("cls");
    secondgamemiro();
    //플레이어 출력
    gotoxy(player.x, player.y);
    printf("□");
   

}
void MovePlayer2()
{
    if (isKeyDown(VK_LEFT))
        player.x--;
    if (isKeyDown(VK_RIGHT))
        player.x++;
    if (isKeyDown(VK_UP))
        player.y--;
    if (isKeyDown(VK_DOWN))
        player.y++;



}
void brandpicture()
{
    printf(" \n \n \n \n");
    printf("                  ■■■■     ■■■      ■■■       ■       ■■■■     ■■■■\n");
    printf("                  ■          ■          ■          ■  ■     ■     ■    ■\n");
    printf("                  ■■■■     ■■■■   ■         ■■■■    ■■■■     ■■■■\n");
    printf("                  ■                  ■  ■         ■    ■    ■           ■\n");
    printf("                  ■■■■     ■■■■    ■■■    ■    ■    ■           ■■■■\n");
    printf("\n");
    printf("                         ■■■        ■■■      ■■■       ■■    ■■\n");
    printf("                         ■   ■      ■     ■   ■     ■     ■ ■  ■ ■\n");
    printf("                         ■■■       ■     ■   ■     ■     ■   ■   ■\n");
    printf("                         ■   ■      ■     ■   ■     ■     ■        ■\n");
    printf("                         ■    ■      ■■■      ■■■       ■        ■\n");
}
void secondgamemiro()
{
    printf("                ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■            ■■■■■■■■■■■■■■■■■■■■■■■■■■\n");
    printf("                ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■            ■■■■■■■■■■■■■■■■■■■■■■■■■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                                                                      ■■            ■■                                            ■■\n");
    printf("                ■■                           ■■■■■■■■■■■■                   ■■            ■■                 ■■■■■                 ■■\n");
    printf("                ■■                           ■■■■■■■■■■■■                   ■■            ■■                 ■■■■■                 ■■\n");
    printf("■■■■■■■■■■                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■■■■■■■■■                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                                           ■■                ■■                   ■■            ■■                 ■■  ■■                 ■■ \n");
    printf("■■                 ■■■■■■■■■■■■■■■                ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■■■■■■■■■■■■■■■■■■■■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■                 ■■■■■■■■■■■■■■■■■■■■■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■\n");
    printf("■■                 ■■                                          ■■                   ■■            ■■                 ■■  ■■\n");
    printf("■■                 ■■                                          ■■                   ■■■■■■■■■■                 ■■  ■■\n");
    printf("■■                 ■■                                          ■■                   ■■■■■■■■■■                 ■■  ■■\n");
    printf("■■                 ■■                                          ■■                                                        ■■  ■■\n");
    printf("■■                 ■■                                          ■■                                                        ■■  ■■\n");
    printf("■■                 ■■                                          ■■                                                        ■■  ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■\n");
    printf("■■                 ■■                                          ■■                                                        ■■  ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■ \n");
    printf("■■                 ■■                                          ■■                                                        ■■ \n");
    printf("■■                 ■■                                          ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■ \n");
    printf("■■                 ■■                                          ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■ \n");

}

void titleDraw() {
    int i;
    //문 출력
    gotoxy(0, HEIGHT + 1);
    for (i = 0; i < WIDTH + 2; i++)
        printf("■");
    gotoxy(0, 0);
    for (i = 0; i < WIDTH + 2; i++)
        printf("■");
    gotoxy(0, 0);
    for (i = 0; i < HEIGHT + 1; i++)
        printf("■\n");
    for (i = 0; i < HEIGHT + 1; i++) {
        gotoxy(WIDTH + 1, i + 1);
        printf("■\n");
    }
    gotoxy(25, HEIGHT / 2);
    printf("■■■\n");
    gotoxy(25, HEIGHT / 2 - 1);
    printf("■■■\n");
    gotoxy(25, HEIGHT / 2 - 2);
    printf("■■■\n");
}
void menuDraw() {
    gotoxy(WIDTH / 2 - 10, 10);
    printf("┌─-───────────────────────────────────────────┐\n");
    gotoxy(WIDTH / 2 - 10, 11);
    printf(" |            방에 들어가시겠습니까?          |\n");
    gotoxy(WIDTH / 2 - 10, 12);
    printf(" |                    > Y                     |\n");
    gotoxy(WIDTH / 2 - 10, 13);
    printf(" |                    > N                     |\n");
    gotoxy(WIDTH / 2 - 10, 14);
    printf("└───-─────────────────────────────────────────┘");
}



//// main 함수 ////
void main(void)
{
    system("mode con cols=110 lines=50 | title 게임제목 ");
    startpicture();
    init();

    do {
        //매번 실행할 때마다 다른 값을 주기 위한 시드값 설정
        srand((int)malloc(NULL));

        CreateEnemy();
        FallEnemy();
        DelEnemy();

        MovePlayer();

        PrintGame();
        //게임의 속도 조절을 위해 Sleep 설정
        Sleep(100);
    } while (DamagedPlayer()==0);    //닿지 않으면 반복
}
