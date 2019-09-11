#include "udf.h"
DEFINE_INIT(domainInit, d)
{
	cell_t c;/*定义变量C*/
	Thread *t;/*定义指针变量t*/
	real xc[ND_ND];/*定义数组xc*/
	real x;/*定义变量*/
	real y;
	thread_loop_c(t, d)/*区域内循环*/
	{
		begin_c_loop_all(c, t)/*网格单元循环*/
		{
			C_CENTROID(xc, c, t);/*获取单元的xyt坐标*/
			x = xc[0];/*获取单元的x坐标*/
			y = xc[1];/*获取单元的y坐标*/
			/*定义椭圆区域*/
			if (x/100 < 1)
			{
				C_T(c, t) = 500;/*设置区域内的温度500k*/
			}
			else
			{
				C_T(c, t) = 300;/*设置区域外的温度300k*/
			}

		}
		end_c_loop_all(c, t)/*结束循环*/
	}
}
