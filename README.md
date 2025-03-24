int[] zp = new int[12];
double[] nal = new double[12];
double[] otkl = new double[12];
Random rand = new Random();
for (int i = 0; i < zp.Length; i++)
    zp[i] = rand.Next(1000,5000);
double sum = 0;
for (int i = 0; i <= 11; i++)
{
    sum += zp[i];
}
for (int i = 0;i <= 11; i++)
{
    nal[i] = zp[i] * 0.02;
}
double sums = sum / 12;
for (int i = 0; i <= 11; i++)
{
    otkl[i] = zp[i] - sums;
}
double nalogY = (sum / 100) * 2;
int minsum  = 5000;
int minnum = 0;
int maxsum  = 0;
int maxnum = 0;
for (int i = 0; i <= 11; i++)
{
     if (minsum > zp[i])
    {
        minsum = zp[i];
        minnum = i;
    }
}
for (int i = 0; i <= 11; i++)
{
    if (maxsum < zp[i])
    {
        maxsum = zp[i];
        maxnum = i + 1;
    }
}
for (int i = 0; i <= 11; i++)
{
    if (minsum > zp[i])
    {
        minsum = zp[i];
        minnum = i + 1;
    }
}
Console.WriteLine($"Доход за год : {sum}");
Console.WriteLine($"Средняя зарплата : {sums:F2}");
Console.WriteLine("Налог по месяцам:{0} ", String.Join(" ", nal));
Console.WriteLine($"Налоги за год : {nalogY:F2}");
Console.WriteLine("Отклонение от средней ЗП:{0} ", String.Join(" ", otkl));
Console.WriteLine($"Минимальная ЗП за год : {minsum}");
Console.WriteLine($"Номер месяца с минимальной ЗП : {minnum}");
Console.WriteLine($"Максимальная ЗП за год : {maxsum}");
Console.WriteLine($"Номер месяца с максимальной ЗП : {maxnum}");
