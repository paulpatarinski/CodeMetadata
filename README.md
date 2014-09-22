CodeMetadata
============

A project that helps you inject metadata into your code using Attributes. 

Example : 

Class without Metadata : 

    namespace Domain
    {
      public class Customer
      {
        private ICustomerDAO _customerDAO;
    
        public Customer(ICustomerDAO customerDAO)
        {
          _customerDAO = customerDAO;
        }
    
        public IEnumerable<object> GetCustomerById(int id)
        {
          return _customerDAO.GetCustomerById(id);
        }
      }
    }

Class with Metadata : 

    [Metadata(Layer = Layers.BusinessLayer, Description = "The Business Layer houses all classes that contain business logic.")]
    namespace Domain
    {
      [Metadata(ClassType = ClassType.Business, Description = "Classes that contain Business Logic.")]
      public class Customer
      {
        private ICustomerDAO _customerDAO;
    
        public Customer(ICustomerDAO customerDAO)
        {
          _customerDAO = customerDAO;
        }
    
        public IEnumerable<object> GetCustomerById(int id)
        {
          return _customerDAO.GetCustomerById(id);
        }
      }
    }
