import { Card, CardContent } from "@/components/ui/card";
import { BarChart, Bar, XAxis, YAxis, Tooltip, ResponsiveContainer } from "recharts";
import { AlertTriangle, Package, ShoppingCart, TrendingUp } from "lucide-react";

const salesData = [
  { name: "Jan", sales: 4000 },
  { name: "Feb", sales: 3000 },
  { name: "Mar", sales: 5000 },
  { name: "Apr", sales: 7000 },
  { name: "May", sales: 6000 },
  { name: "Jun", sales: 8000 },
  { name: "Jul", sales: 6500 },
  { name: "Aug", sales: 7200 },
  { name: "Sep", sales: 5400 },
  { name: "Oct", sales: 7800 },
  { name: "Nov", sales: 6900 },
  { name: "Dec", sales: 8100 },
];

const Dashboard = () => {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 p-4">
      <Card>
        <CardContent className="flex items-center p-4">
          <Package className="text-blue-500 w-8 h-8" />
          <div className="ml-4">
            <p className="text-sm text-gray-500">المخزون المتاح</p>
            <p className="text-xl font-bold">{Math.floor(Math.random() * 2000)}</p>
          </div>
        </CardContent>
      </Card>
      <Card>
        <CardContent className="flex items-center p-4">
          <ShoppingCart className="text-green-500 w-8 h-8" />
          <div className="ml-4">
            <p className="text-sm text-gray-500">المبيعات اليوم</p>
            <p className="text-xl font-bold">{Math.floor(Math.random() * 500)}</p>
          </div>
        </CardContent>
      </Card>
      <Card>
        <CardContent className="flex items-center p-4">
          <TrendingUp className="text-purple-500 w-8 h-8" />
          <div className="ml-4">
            <p className="text-sm text-gray-500">المنتج الأكثر مبيعًا</p>
            <p className="text-xl font-bold">منتج {Math.floor(Math.random() * 100)}</p>
          </div>
        </CardContent>
      </Card>
      <Card>
        <CardContent className="flex items-center p-4">
          <AlertTriangle className="text-red-500 w-8 h-8" />
          <div className="ml-4">
            <p className="text-sm text-gray-500">تنبيهات المخزون</p>
            <p className="text-xl font-bold">{Math.floor(Math.random() * 10)} منتجات منخفضة</p>
          </div>
        </CardContent>
      </Card>
      <Card className="col-span-1 md:col-span-2 lg:col-span-4">
        <CardContent className="p-4">
          <h3 className="text-lg font-bold">إحصائيات المبيعات</h3>
          <ResponsiveContainer width="100%" height={300}>
            <BarChart data={salesData}>
              <XAxis dataKey="name" />
              <YAxis />
              <Tooltip />
              <Bar dataKey="sales" fill="#4F46E5" />
            </BarChart>
          </ResponsiveContainer>
        </CardContent>
      </Card>
    </div>
  );
};

export default Dashboard;
