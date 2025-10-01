<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bill Tracker</title>
  <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
</head>
<body>
  <div id="root"></div>
  
  <script type="text/babel">
    const { useState, useEffect } = React;

    // Icon components
    const Calendar = (props) => <i data-lucide="calendar" {...props}></i>;
    const DollarSign = (props) => <i data-lucide="dollar-sign" {...props}></i>;
    const Plus = (props) => <i data-lucide="plus" {...props}></i>;
    const Eye = (props) => <i data-lucide="eye" {...props}></i>;
    const EyeOff = (props) => <i data-lucide="eye-off" {...props}></i>;
    const Trash2 = (props) => <i data-lucide="trash-2" {...props}></i>;
    const Check = (props) => <i data-lucide="check" {...props}></i>;
    const X = (props) => <i data-lucide="x" {...props}></i>;
    const Building2 = (props) => <i data-lucide="building-2" {...props}></i>;
    const User = (props) => <i data-lucide="user" {...props}></i>;
    const TrendingUp = (props) => <i data-lucide="trending-up" {...props}></i>;

    const BillTracker = () => {
      const [isLoggedIn, setIsLoggedIn] = useState(false);
      const [username, setUsername] = useState('');
      const [password, setPassword] = useState('');
      const [bills, setBills] = useState([]);
      const [showAddBill, setShowAddBill] = useState(false);
      const [selectedCategory, setSelectedCategory] = useState('all');
      const [showPasswords, setShowPasswords] = useState({});
      const [view, setView] = useState('upcoming');

      const [newBill, setNewBill] = useState({
        vendor: '',
        category: 'personal',
        email: '',
        username: '',
        password: '',
        dueDate: '',
        amount: '',
        frequency: 'monthly',
        notes: ''
      });

      useEffect(() => {
        const savedBills = localStorage.getItem('bills');
        const savedUser = localStorage.getItem('loggedInUser');
        if (savedBills) setBills(JSON.parse(savedBills));
        if (savedUser) {
          setIsLoggedIn(true);
          setUsername(savedUser);
        }
      }, []);

      useEffect(() => {
        if (bills.length > 0) {
          localStorage.setItem('bills', JSON.stringify(bills));
        }
      }, [bills]);

      useEffect(() => {
        lucide.createIcons();
      });

      const handleLogin = () => {
        if (username && password) {
          setIsLoggedIn(true);
          localStorage.setItem('loggedInUser', username);
        }
      };

      const handleLogout = () => {
        setIsLoggedIn(false);
        setUsername('');
        setPassword('');
        localStorage.removeItem('loggedInUser');
      };

      const addBill = () => {
        if (newBill.vendor && newBill.amount && newBill.dueDate) {
          const bill = {
            ...newBill,
            id: Date.now(),
            paid: false,
            history: []
          };
          setBills([...bills, bill]);
          setNewBill({
            vendor: '',
            category: 'personal',
            email: '',
            username: '',
            password: '',
            dueDate: '',
            amount: '',
            frequency: 'monthly',
            notes: ''
          });
          setShowAddBill(false);
        }
      };

      const togglePaid = (id) => {
        setBills(bills.map(bill => {
          if (bill.id === id) {
            const updatedBill = { ...bill, paid: !bill.paid };
            if (!bill.paid) {
              updatedBill.history = [...(bill.history || []), {
                date: new Date().toISOString(),
                amount: bill.amount
              }];
            }
            return updatedBill;
          }
          return bill;
        }));
      };

      const deleteBill = (id) => {
        setBills(bills.filter(bill => bill.id !== id));
      };

      const togglePasswordVisibility = (id) => {
        setShowPasswords(prev => ({ ...prev, [id]: !prev[id] }));
      };

      const calculateStatus = (dueDate, paid) => {
        if (paid) return 'paid';
        const today = new Date();
        const due = new Date(dueDate);
        const daysUntil = Math.ceil((due - today) / (1000 * 60 * 60 * 24));
        
        if (daysUntil < 0) return 'overdue';
        if (daysUntil <= 3) return 'due-soon';
        return 'upcoming';
      };

      const getStatusColor = (status) => {
        switch(status) {
          case 'overdue': return 'bg-red-100 text-red-800 border-red-300';
          case 'due-soon': return 'bg-yellow-100 text-yellow-800 border-yellow-300';
          case 'paid': return 'bg-green-100 text-green-800 border-green-300';
          default: return 'bg-blue-100 text-blue-800 border-blue-300';
        }
      };

      const filteredBills = bills.filter(bill => {
        if (selectedCategory !== 'all' && bill.category !== selectedCategory) return false;
        if (view === 'upcoming') return !bill.paid;
        if (view === 'paid') return bill.paid;
        return true;
      });

      const totalDue = filteredBills
        .filter(bill => !bill.paid)
        .reduce((sum, bill) => sum + parseFloat(bill.amount || 0), 0);

      const categories = ['all', 'personal', 'business1', 'business2', 'business3'];

      if (!isLoggedIn) {
        return (
          <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 flex items-center justify-center p-4">
            <div className="bg-white rounded-2xl shadow-2xl p-8 w-full max-w-md">
              <div className="text-center mb-8">
                <div className="bg-indigo-600 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                  <DollarSign className="text-white" size={32} />
                </div>
                <h1 className="text-3xl font-bold text-gray-800">Bill Tracker</h1>
                <p className="text-gray-600 mt-2">Manage your personal and business expenses</p>
              </div>
              <div className="space-y-4">
                <div>
                  <label className="block text-sm font-medium text-gray-700 mb-2">Username</label>
                  <input
                    type="text"
                    value={username}
                    onChange={(e) => setUsername(e.target.value)}
                    className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                    placeholder="Enter username"
                  />
                </div>
                <div>
                  <label className="block text-sm font-medium text-gray-700 mb-2">Password</label>
                  <input
                    type="password"
                    value={password}
                    onChange={(e) => setPassword(e.target.value)}
                    onKeyPress={(e) => e.key === 'Enter' && handleLogin()}
                    className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                    placeholder="Enter password"
                  />
                </div>
                <button
                  onClick={handleLogin}
                  className="w-full bg-indigo-600 text-white py-3 rounded-lg hover:bg-indigo-700 transition font-semibold"
                >
                  Login
                </button>
              </div>
            </div>
          </div>
        );
      }

      return (
        <div className="min-h-screen bg-gray-50">
          <header className="bg-white shadow-sm border-b">
            <div className="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
              <div className="flex items-center gap-3">
                <div className="bg-indigo-600 p-2 rounded-lg">
                  <DollarSign className="text-white" size={24} />
                </div>
                <div>
                  <h1 className="text-2xl font-bold text-gray-800">Bill Tracker</h1>
                  <p className="text-sm text-gray-600">Welcome, {username}</p>
                </div>
              </div>
              <button
                onClick={handleLogout}
                className="px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600 transition"
              >
                Logout
              </button>
            </div>
          </header>

          <main className="max-w-7xl mx-auto p-4 md:p-6">
            <div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
              <div className="bg-white rounded-xl shadow p-6 border-l-4 border-indigo-500">
                <div className="flex items-center justify-between">
                  <div>
                    <p className="text-gray-600 text-sm font-medium">Total Due</p>
                    <p className="text-3xl font-bold text-gray-800">${totalDue.toFixed(2)}</p>
                  </div>
                  <TrendingUp className="text-indigo-500" size={32} />
                </div>
              </div>
              <div className="bg-white rounded-xl shadow p-6 border-l-4 border-yellow-500">
                <div className="flex items-center justify-between">
                  <div>
                    <p className="text-gray-600 text-sm font-medium">Upcoming Bills</p>
                    <p className="text-3xl font-bold text-gray-800">
                      {bills.filter(b => !b.paid).length}
                    </p>
                  </div>
                  <Calendar className="text-yellow-500" size={32} />
                </div>
              </div>
              <div className="bg-white rounded-xl shadow p-6 border-l-4 border-green-500">
                <div className="flex items-center justify-between">
                  <div>
                    <p className="text-gray-600 text-sm font-medium">Paid This Month</p>
                    <p className="text-3xl font-bold text-gray-800">
                      {bills.filter(b => b.paid).length}
                    </p>
                  </div>
                  <Check className="text-green-500" size={32} />
                </div>
              </div>
            </div>

            <div className="bg-white rounded-xl shadow mb-6">
              <div className="p-4 border-b flex flex-wrap gap-2 items-center justify-between">
                <div className="flex gap-2 flex-wrap">
                  <button
                    onClick={() => setView('upcoming')}
                    className={`px-4 py-2 rounded-lg transition ${view === 'upcoming' ? 'bg-indigo-600 text-white' : 'bg-gray-100 text-gray-700 hover:bg-gray-200'}`}
                  >
                    Upcoming
                  </button>
                  <button
                    onClick={() => setView('paid')}
                    className={`px-4 py-2 rounded-lg transition ${view === 'paid' ? 'bg-indigo-600 text-white' : 'bg-gray-100 text-gray-700 hover:bg-gray-200'}`}
                  >
                    Paid
                  </button>
                  <button
                    onClick={() => setView('all')}
                    className={`px-4 py-2 rounded-lg transition ${view === 'all' ? 'bg-indigo-600 text-white' : 'bg-gray-100 text-gray-700 hover:bg-gray-200'}`}
                  >
                    All Bills
                  </button>
                </div>
                <button
                  onClick={() => setShowAddBill(true)}
                  className="px-4 py-2 bg-indigo-600 text-white rounded-lg hover:bg-indigo-700 transition flex items-center gap-2"
                >
                  <Plus size={20} />
                  Add Bill
                </button>
              </div>

              <div className="p-4 border-b">
                <div className="flex gap-2 flex-wrap">
                  {categories.map(cat => (
                    <button
                      key={cat}
                      onClick={() => setSelectedCategory(cat)}
                      className={`px-4 py-2 rounded-lg transition capitalize ${
                        selectedCategory === cat 
                          ? 'bg-indigo-100 text-indigo-700 border border-indigo-300' 
                          : 'bg-gray-50 text-gray-700 hover:bg-gray-100 border border-gray-200'
                      }`}
                    >
                      {cat === 'all' ? 'All' : cat}
                    </button>
                  ))}
                </div>
              </div>

              <div className="overflow-x-auto">
                <table className="w-full">
                  <thead className="bg-gray-50 border-b">
                    <tr>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Status</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Vendor</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Category</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Due Date</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Amount</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Credentials</th>
                      <th className="px-4 py-3 text-left text-sm font-semibold text-gray-700">Actions</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y">
                    {filteredBills.length === 0 ? (
                      <tr>
                        <td colSpan="7" className="px-4 py-8 text-center text-gray-500">
                          No bills found. Add your first bill to get started!
                        </td>
                      </tr>
                    ) : (
                      filteredBills.map(bill => {
                        const status = calculateStatus(bill.dueDate, bill.paid);
                        return (
                          <tr key={bill.id} className="hover:bg-gray-50">
                            <td className="px-4 py-4">
                              <span className={`px-3 py-1 rounded-full text-xs font-semibold border ${getStatusColor(status)}`}>
                                {status === 'due-soon' ? 'Due Soon' : status.charAt(0).toUpperCase() + status.slice(1)}
                              </span>
                            </td>
                            <td className="px-4 py-4">
                              <div className="font-medium text-gray-800">{bill.vendor}</div>
                              {bill.notes && <div className="text-sm text-gray-500">{bill.notes}</div>}
                            </td>
                            <td className="px-4 py-4">
                              <span className="inline-flex items-center gap-1 px-2 py-1 bg-gray-100 rounded text-sm capitalize">
                                {bill.category === 'personal' ? <User size={14} /> : <Building2 size={14} />}
                                {bill.category}
                              </span>
                            </td>
                            <td className="px-4 py-4 text-gray-700">
                              {new Date(bill.dueDate).toLocaleDateString()}
                            </td>
                            <td className="px-4 py-4">
                              <span className="font-semibold text-gray-800">${parseFloat(bill.amount).toFixed(2)}</span>
                            </td>
                            <td className="px-4 py-4">
                              <div className="space-y-1 text-sm">
                                {bill.email && <div className="text-gray-600">Email: {bill.email}</div>}
                                {bill.username && <div className="text-gray-600">User: {bill.username}</div>}
                                {bill.password && (
                                  <div className="flex items-center gap-2">
                                    <span className="text-gray-600">
                                      Pass: {showPasswords[bill.id] ? bill.password : '••••••••'}
                                    </span>
                                    <button
                                      onClick={() => togglePasswordVisibility(bill.id)}
                                      className="text-indigo-600 hover:text-indigo-700"
                                    >
                                      {showPasswords[bill.id] ? <EyeOff size={16} /> : <Eye size={16} />}
                                    </button>
                                  </div>
                                )}
                              </div>
                            </td>
                            <td className="px-4 py-4">
                              <div className="flex gap-2">
                                <button
                                  onClick={() => togglePaid(bill.id)}
                                  className={`p-2 rounded-lg transition ${
                                    bill.paid 
                                      ? 'bg-gray-100 text-gray-600 hover:bg-gray-200' 
                                      : 'bg-green-100 text-green-700 hover:bg-green-200'
                                  }`}
                                  title={bill.paid ? 'Mark as unpaid' : 'Mark as paid'}
                                >
                                  <Check size={18} />
                                </button>
                                <button
                                  onClick={() => deleteBill(bill.id)}
                                  className="p-2 bg-red-100 text-red-700 rounded-lg hover:bg-red-200 transition"
                                  title="Delete bill"
                                >
                                  <Trash2 size={18} />
                                </button>
                              </div>
                            </td>
                          </tr>
                        );
                      })
                    )}
                  </tbody>
                </table>
              </div>
            </div>
          </main>

          {showAddBill && (
            <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 z-50">
              <div className="bg-white rounded-xl shadow-2xl max-w-2xl w-full max-h-[90vh] overflow-y-auto">
                <div className="p-6 border-b flex justify-between items-center">
                  <h2 className="text-2xl font-bold text-gray-800">Add New Bill</h2>
                  <button
                    onClick={() => setShowAddBill(false)}
                    className="p-2 hover:bg-gray-100 rounded-lg transition"
                  >
                    <X size={24} />
                  </button>
                </div>
                <div className="p-6 space-y-4">
                  <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Vendor/Service *</label>
                      <input
                        type="text"
                        value={newBill.vendor}
                        onChange={(e) => setNewBill({...newBill, vendor: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                        placeholder="Netflix, Electric Company, etc."
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Category *</label>
                      <select
                        value={newBill.category}
                        onChange={(e) => setNewBill({...newBill, category: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                      >
                        <option value="personal">Personal</option>
                        <option value="business1">Business 1</option>
                        <option value="business2">Business 2</option>
                        <option value="business3">Business 3</option>
                      </select>
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Amount *</label>
                      <input
                        type="number"
                        step="0.01"
                        value={newBill.amount}
                        onChange={(e) => setNewBill({...newBill, amount: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                        placeholder="0.00"
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Due Date *</label>
                      <input
                        type="date"
                        value={newBill.dueDate}
                        onChange={(e) => setNewBill({...newBill, dueDate: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Email</label>
                      <input
                        type="email"
                        value={newBill.email}
                        onChange={(e) => setNewBill({...newBill, email: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                        placeholder="your@email.com"
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Username</label>
                      <input
                        type="text"
                        value={newBill.username}
                        onChange={(e) => setNewBill({...newBill, username: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                        placeholder="account username"
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Password</label>
                      <input
                        type="password"
                        value={newBill.password}
                        onChange={(e) => setNewBill({...newBill, password: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                        placeholder="account password"
                      />
                    </div>
                    <div>
                      <label className="block text-sm font-medium text-gray-700 mb-2">Frequency</label>
                      <select
                        value={newBill.frequency}
                        onChange={(e) => setNewBill({...newBill, frequency: e.target.value})}
                        className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                      >
                        <option value="weekly">Weekly</option>
                        <option value="monthly">Monthly</option>
                        <option value="quarterly">Quarterly</option>
                        <option value="yearly">Yearly</option>
                      </select>
                    </div>
                  </div>
                  <div>
                    <label className="block text-sm font-medium text-gray-700 mb-2">Notes</label>
                    <textarea
                      value={newBill.notes}
                      onChange={(e) => setNewBill({...newBill, notes: e.target.value})}
                      className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-transparent"
                      rows="3"
                      placeholder="Additional notes about this bill..."
                    />
                  </div>
                </div>
                <div className="p-6 border-t flex gap-3 justify-end">
                  <button
                    onClick={() => setShowAddBill(false)}
                    className="px-6 py-2 border border-gray-300 text-gray-700 rounded-lg hover:bg-gray-50 transition"
                  >
                    Cancel
                  </button>
                  <button
                    onClick={addBill}
                    className="px-6 py-2 bg-indigo-600 text-white rounded-lg hover:bg-indigo-700 transition"
                  >
                    Add Bill
                  </button>
                </div>
              </div>
            </div>
          )}
        </div>
      );
    };

    ReactDOM.render(<BillTracker />, document.getElementById('root'));
  </script>
</body>
</html>
