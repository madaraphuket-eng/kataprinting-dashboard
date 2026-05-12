export default function CommissionDashboard() {
  return (
    <div className="min-h-screen bg-gray-100 p-6">
      <div className="max-w-6xl mx-auto">
        <h1 className="text-3xl font-bold mb-6">Dashboard ค่าคอมป้ายไฟ</h1>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
          <div className="bg-white rounded-2xl shadow p-6">
            <p className="text-gray-500">ยอดขายรวม</p>
            <h2 className="text-3xl font-bold mt-2">51,780 บาท</h2>
          </div>

          <div className="bg-white rounded-2xl shadow p-6">
            <p className="text-gray-500">ค่าคอม 7%</p>
            <h2 className="text-3xl font-bold mt-2">3,624.60 บาท</h2>
          </div>

          <div className="bg-white rounded-2xl shadow p-6">
            <p className="text-gray-500">จำนวนที่ขาย</p>
            <h2 className="text-3xl font-bold mt-2">18 ชิ้น</h2>
          </div>
        </div>

        <div className="bg-white rounded-2xl shadow p-6 overflow-x-auto">
          <h2 className="text-xl font-semibold mb-4">รายการขาย</h2>

          <table className="w-full border-collapse">
            <thead>
              <tr className="border-b text-left">
                <th className="py-3">วันที่</th>
                <th>ขนาด</th>
                <th>ราคาต่อชิ้น</th>
                <th>จำนวน</th>
                <th>ยอดขาย</th>
                <th>ค่าคอม</th>
              </tr>
            </thead>
            <tbody>
              {[
                ['1-5-69', '28×145', 3890, 1],
                ['7-5-69', '20×63', 2490, 2],
                ['8-5-69', '12×59', 850, 1],
                ['8-5-69', '28×192', 5490, 1],
                ['8-5-69', '12×59', 850, 1],
                ['8-5-69', '19×133', 2790, 1],
                ['9-5-69', '12×59', 850, 2],
                ['10-5-69', '19×133', 2790, 1],
                ['10-5-69', '28×192', 5490, 1],
                ['10-5-69', '20×63', 2490, 1],
                ['10-5-69', '12×59', 850, 1],
                ['11-5-69', '12×59', 850, 1],
                ['11-5-69', '28×192', 5490, 1],
                ['12-5-69', '20×63', 2490, 1],
                ['12-5-69', '29×240', 6890, 1],
                ['12-5-69', '19×175', 3890, 1],
              ].map((item, index) => {
                const total = item[2] * item[3]
                const commission = total * 0.07

                return (
                  <tr key={index} className="border-b hover:bg-gray-50">
                    <td className="py-3">{item[0]}</td>
                    <td>{item[1]}</td>
                    <td>{item[2].toLocaleString()} บาท</td>
                    <td>{item[3]}</td>
                    <td>{total.toLocaleString()} บาท</td>
                    <td>{commission.toLocaleString(undefined, { maximumFractionDigits: 2 })} บาท</td>
                  </tr>
                )
              })}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  )
}

