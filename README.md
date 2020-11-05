# Container
My first repository on GitHub
class Solution {
    public int maxArea(int[] height) {
			int size = height.length;
		int m1 = 0, m2 = 0,i=0,j=0;

		for (i=0; i<size; i++)
		{
			for (j=0; j<size; j++)
			{
				if (height[i] <= height[j] && i!=j)
				{
					m1 = height[i] * (j-i);
					
					if (m1<0)
					{
						m1=m1*(-1);
					}

					if (m1 > m2)
					{
						m2=m1;
					}
				}
				if (height[i] > height[j] && i!=j)
				{
					m1 = height[j] * (i-j);

					if (m1<0)
					{
						m1=m1*(-1);
					}

					if (m1 > m2)
					{
						m2=m1;
					}
				}
			}
		}

		return m2;
    }
}
