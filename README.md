Database(1): `channel_me_test`
--

-- --------------------------------------------------------

--
-- Table structure for table `adddoctors`
--

CREATE TABLE `adddoctors` (
  `doctor_id` varchar(20) NOT NULL,
  `doctor_name` varchar(255) NOT NULL,
  `images` text DEFAULT NULL,
  `specialization_id` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `adddoctors`
--

INSERT INTO `adddoctors` (`doctor_id`, `doctor_name`, `images`, `specialization_id`) VALUES
('D001', 'Perera', 'uploads/doctors/1742710346_1741099583_profile.jpg', 'SP001'),
('D002', 'Malaka', 'uploads/doctors/1742714559_1741604063_prof-sir-romesh-jayasinghe-ols-psychologist-therapytribe-161115.jpg', 'SP003'),
('D003', 'Disanayake', 'uploads/doctors/1742714607_1741595495_dr-shailendra-ganjewar-jpeg_1663131500.jpg', 'SP008'),
('D004', 'Ediriweera', 'uploads/doctors/1742714630_1741100913_d1.webp', 'SP001');

-- --------------------------------------------------------

--
-- Table structure for table `appointments`
--

CREATE TABLE `appointments` (
  `appointment_id` int(11) NOT NULL,
  `user_id` varchar(10) NOT NULL,
  `patient_name` varchar(255) NOT NULL,
  `patient_email` varchar(255) NOT NULL,
  `appointment_day` varchar(10) DEFAULT NULL,
  `appointment_time` varchar(20) NOT NULL,
  `notes` text DEFAULT NULL,
  `created_at` timestamp NOT NULL DEFAULT current_timestamp(),
  `doctor_name` varchar(255) NOT NULL,
  `status` enum('Pending','Confirmed','Cancelled') DEFAULT 'Pending'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `appointments`
--

INSERT INTO `appointments` (`appointment_id`, `user_id`, `patient_name`, `patient_email`, `appointment_day`, `appointment_time`, `notes`, `created_at`, `doctor_name`, `status`) VALUES
(12, 'C-012', 'Sanduni sewwandi', 'sanduni2003822madu@gmail.com', 'Monday', '07:00:00 - 09:00:00', 'Hi', '2025-04-02 06:29:21', 'Dr. Malaka', 'Confirmed'),
(13, 'C-013', 'Sandali Malnethmi', 'sanmalhas19@gmail.com', 'Wednesday', '13:00:00 - 15:00:00', 'hi,hi', '2025-04-02 08:46:32', 'Dr. Malaka', 'Pending');

-- --------------------------------------------------------

--
-- Table structure for table `doctorregister`
--

CREATE TABLE `doctorregister` (
  `doctor_id` int(11) NOT NULL,
  `user_id` varchar(10) NOT NULL,
  `doctor_name` varchar(255) NOT NULL,
  `specialization_id` varchar(20) NOT NULL,
  `images` text NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `doctorregister`
--

INSERT INTO `doctorregister` (`doctor_id`, `user_id`, `doctor_name`, `specialization_id`, `images`) VALUES
(5, 'D-002', 'Malaka', 'SP001', 'uploads/doctors/1743498102_1741099877_profile.jpg'),
(6, 'D-003', 'Sanjaya', 'SP001', 'uploads/doctors/1743516348_1741489210_dpro.jpg'),
(7, 'D-004', 'Nimalka', 'SP008', 'uploads/doctors/1743516783_1742321728_staff.jpg'),
(8, 'D-005', 'Darshana', 'SP003', 'uploads/doctors/1743517118_1741595942_prof-sir-romesh-jayasinghe-ols-psychologist-therapytribe-161115.jpg');

-- --------------------------------------------------------

--
-- Table structure for table `doctor_schedule`
--

CREATE TABLE `doctor_schedule` (
  `id` int(11) NOT NULL,
  `user_id` varchar(10) NOT NULL,
  `specialization_id` varchar(20) DEFAULT NULL,
  `monday_morning_start` time DEFAULT NULL,
  `monday_morning_end` time DEFAULT NULL,
  `monday_evening_start` time DEFAULT NULL,
  `monday_evening_end` time DEFAULT NULL,
  `tuesday_morning_start` time DEFAULT NULL,
  `tuesday_morning_end` time DEFAULT NULL,
  `tuesday_evening_start` time DEFAULT NULL,
  `tuesday_evening_end` time DEFAULT NULL,
  `wednesday_morning_start` time DEFAULT NULL,
  `wednesday_morning_end` time DEFAULT NULL,
  `wednesday_evening_start` time DEFAULT NULL,
  `wednesday_evening_end` time DEFAULT NULL,
  `thursday_morning_start` time DEFAULT NULL,
  `thursday_morning_end` time DEFAULT NULL,
  `thursday_evening_start` time DEFAULT NULL,
  `thursday_evening_end` time DEFAULT NULL,
  `friday_morning_start` time DEFAULT NULL,
  `friday_morning_end` time DEFAULT NULL,
  `friday_evening_start` time DEFAULT NULL,
  `friday_evening_end` time DEFAULT NULL,
  `saturday_morning_start` time DEFAULT NULL,
  `saturday_morning_end` time DEFAULT NULL,
  `saturday_evening_start` time DEFAULT NULL,
  `saturday_evening_end` time DEFAULT NULL,
  `sunday_morning_start` time DEFAULT NULL,
  `sunday_morning_end` time DEFAULT NULL,
  `sunday_evening_start` time DEFAULT NULL,
  `sunday_evening_end` time DEFAULT NULL,
  `monday_morning_max` int(11) NOT NULL DEFAULT 0,
  `monday_evening_max` int(11) NOT NULL DEFAULT 0,
  `tuesday_morning_max` int(11) NOT NULL DEFAULT 0,
  `tuesday_evening_max` int(11) NOT NULL DEFAULT 0,
  `wednesday_morning_max` int(11) NOT NULL DEFAULT 0,
  `wednesday_evening_max` int(11) NOT NULL DEFAULT 0,
  `thursday_morning_max` int(11) NOT NULL DEFAULT 0,
  `thursday_evening_max` int(11) NOT NULL DEFAULT 0,
  `friday_morning_max` int(11) NOT NULL DEFAULT 0,
  `friday_evening_max` int(11) NOT NULL DEFAULT 0,
  `saturday_morning_max` int(11) NOT NULL DEFAULT 0,
  `saturday_evening_max` int(11) NOT NULL DEFAULT 0,
  `sunday_morning_max` int(11) NOT NULL DEFAULT 0,
  `sunday_evening_max` int(11) NOT NULL DEFAULT 0
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `doctor_schedule`
--

INSERT INTO `doctor_schedule` (`id`, `user_id`, `specialization_id`, `monday_morning_start`, `monday_morning_end`, `monday_evening_start`, `monday_evening_end`, `tuesday_morning_start`, `tuesday_morning_end`, `tuesday_evening_start`, `tuesday_evening_end`, `wednesday_morning_start`, `wednesday_morning_end`, `wednesday_evening_start`, `wednesday_evening_end`, `thursday_morning_start`, `thursday_morning_end`, `thursday_evening_start`, `thursday_evening_end`, `friday_morning_start`, `friday_morning_end`, `friday_evening_start`, `friday_evening_end`, `saturday_morning_start`, `saturday_morning_end`, `saturday_evening_start`, `saturday_evening_end`, `sunday_morning_start`, `sunday_morning_end`, `sunday_evening_start`, `sunday_evening_end`, `monday_morning_max`, `monday_evening_max`, `tuesday_morning_max`, `tuesday_evening_max`, `wednesday_morning_max`, `wednesday_evening_max`, `thursday_morning_max`, `thursday_evening_max`, `friday_morning_max`, `friday_evening_max`, `saturday_morning_max`, `saturday_evening_max`, `sunday_morning_max`, `sunday_evening_max`) VALUES
(2, 'D-002', 'SP001', '07:00:00', '09:00:00', '12:00:00', '14:00:00', '08:00:00', '10:00:00', '15:00:00', '17:00:00', '09:30:00', '11:30:00', '13:00:00', '15:00:00', '08:30:00', '10:30:00', '16:00:00', '18:00:00', '07:30:00', '09:30:00', '17:00:00', '19:00:00', '08:55:00', '10:00:00', '18:00:00', '20:00:00', '08:00:00', '11:00:00', '19:00:00', '21:30:00', 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10);

-- --------------------------------------------------------

--
-- Table structure for table `inquiries`
--

CREATE TABLE `inquiries` (
  `id` int(11) NOT NULL,
  `client_name` varchar(255) NOT NULL,
  `subject` varchar(255) NOT NULL,
  `inquiry_date` date NOT NULL,
  `message` text NOT NULL,
  `images` text DEFAULT NULL,
  `created_at` timestamp NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `inquiries`
--

INSERT INTO `inquiries` (`id`, `client_name`, `subject`, `inquiry_date`, `message`, `images`, `created_at`) VALUES
(1, 'sanduni', 'what are the symptoms of diabetes', '2025-03-06', 'I want to know about symptoms of   diadetes', '', '2025-03-28 16:25:51'),
(2, 'sanduni', 'what are the symptoms of diabetes', '2025-03-06', 'I want to know about symptoms of   diadetes', '', '2025-03-28 16:35:29'),
(3, 'sanduni', 'what are the symptoms of diabetes', '2025-03-06', 'I want to know about symptoms of   diadetes', '', '2025-03-28 16:38:39'),
(4, 'sanduni', 'what are the symptoms of diabetes', '2025-03-06', 'I want to know about symptoms of   diadetes', '', '2025-03-28 16:41:14'),
(5, 'sanduni', 'Symptoms of diabetes', '2025-03-19', 'I want to know about what are the symptoms of diadetes', '', '2025-03-28 16:42:55'),
(6, 'sanduni', 'Symptoms of diabetes', '2025-03-19', 'I want to know about what are the symptoms of diadetes', '', '2025-03-28 16:45:04'),
(7, 'sanduni', 'Symptoms of diabetes', '2025-03-19', 'I want to know about what are the symptoms of diadetes', '', '2025-03-28 16:48:42'),
(8, 'sanduni', 'Symptoms of diabetes', '2025-03-19', 'I want to know about what are the symptoms of diadetes', '', '2025-03-28 17:03:08'),
(9, 'sanduni', 'Symptoms of diabetes', '2025-03-19', 'I want to know about what are the symptoms of diadetes', 'uploads/25905344239ded1b98f8f6bce9a3f683.jpg,uploads/37bef007130d5662b457ca716a908f8d.jpg,uploads/fba10887f540360e31e93bc2db1817db.jpg', '2025-03-28 17:04:00');

-- --------------------------------------------------------

--
-- Table structure for table `specialization`
--

CREATE TABLE `specialization` (
  `specialization_id` varchar(20) NOT NULL,
  `specialization` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `specialization`
--

INSERT INTO `specialization` (`specialization_id`, `specialization`) VALUES
('SP001', 'Cardiology'),
('SP002', 'Dermatology'),
('SP003', 'Neurology'),
('SP004', 'Orthopedics'),
('SP005', 'Pediatrics'),
('SP006', 'Gynecology'),
('SP007', 'Ophthalmology'),
('SP008', 'Psychiatry'),
('SP009', 'Radiology'),
('SP010', 'Oncology'),
('SP011', 'Urology'),
('SP012', 'Endocrinology'),
('SP013', 'Gastroenterology'),
('SP014', 'Pulmonology'),
('SP015', 'Nephrology');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `adddoctors`
--
ALTER TABLE `adddoctors`
  ADD PRIMARY KEY (`doctor_id`),
  ADD KEY `fk_specialization` (`specialization_id`);

--
-- Indexes for table `appointments`
--
ALTER TABLE `appointments`
  ADD PRIMARY KEY (`appointment_id`),
  ADD KEY `user_id` (`user_id`);

--
-- Indexes for table `doctorregister`
--
ALTER TABLE `doctorregister`
  ADD PRIMARY KEY (`doctor_id`),
  ADD KEY `user_id` (`user_id`),
  ADD KEY `specialization_id` (`specialization_id`);

--
-- Indexes for table `doctor_schedule`
--
ALTER TABLE `doctor_schedule`
  ADD PRIMARY KEY (`id`),
  ADD KEY `fk_user_id` (`user_id`),
  ADD KEY `fk_specialization_id` (`specialization_id`);

--
-- Indexes for table `inquiries`
--
ALTER TABLE `inquiries`
  ADD PRIMARY KEY (`id`);

--
-- Indexes for table `specialization`
--
ALTER TABLE `specialization`
  ADD PRIMARY KEY (`specialization_id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `appointments`
--
ALTER TABLE `appointments`
  MODIFY `appointment_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=14;

--
-- AUTO_INCREMENT for table `doctorregister`
--
ALTER TABLE `doctorregister`
  MODIFY `doctor_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=9;

--
-- AUTO_INCREMENT for table `doctor_schedule`
--
ALTER TABLE `doctor_schedule`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- AUTO_INCREMENT for table `inquiries`
--
ALTER TABLE `inquiries`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=10;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `adddoctors`
--
ALTER TABLE `adddoctors`
  ADD CONSTRAINT `fk_specialization` FOREIGN KEY (`specialization_id`) REFERENCES `specialization` (`specialization_id`);

--
-- Constraints for table `appointments`
--
ALTER TABLE `appointments`
  ADD CONSTRAINT `appointments_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `user_auth_system`.`users` (`user_id`) ON DELETE CASCADE;

--
-- Constraints for table `doctorregister`
--
ALTER TABLE `doctorregister`
  ADD CONSTRAINT `doctorregister_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `user_auth_system`.`users` (`user_id`) ON DELETE CASCADE,
  ADD CONSTRAINT `doctorregister_ibfk_2` FOREIGN KEY (`specialization_id`) REFERENCES `specialization` (`specialization_id`);

--
-- Constraints for table `doctor_schedule`
--
ALTER TABLE `doctor_schedule`
  ADD CONSTRAINT `fk_specialization_id` FOREIGN KEY (`specialization_id`) REFERENCES `specialization` (`specialization_id`) ON DELETE SET NULL,
  ADD CONSTRAINT `fk_user_id` FOREIGN KEY (`user_id`) REFERENCES `user_auth_system`.`users` (`user_id`) ON DELETE CASCADE;




Database(02):


CREATE TABLE `customer_details` (
  `user_id` varchar(10) NOT NULL,
  `gender` enum('male','female','other') NOT NULL,
  `dob` date NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `customer_details`
--

INSERT INTO `customer_details` (`user_id`, `gender`, `dob`) VALUES
('C-001', 'other', '2003-03-03'),
('C-008', 'male', '0000-00-00'),
('C-009', 'male', '2025-03-10'),
('C-010', 'male', '2025-03-05'),
('C-011', 'male', '2025-03-05'),
('C-012', 'male', '2003-08-22'),
('C-013', 'male', '2003-03-12');

-- --------------------------------------------------------

--
-- Table structure for table `doctor_details`
--

CREATE TABLE `doctor_details` (
  `user_id` varchar(10) NOT NULL,
  `work_from` varchar(50) DEFAULT 'retired',
  `medical_type` varchar(100) DEFAULT NULL,
  `description` text DEFAULT NULL,
  `image_path` varchar(255) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `doctor_details`
--

INSERT INTO `doctor_details` (`user_id`, `work_from`, `medical_type`, `description`, `image_path`) VALUES
('D-001', 'retired', '2', '2', '2');

-- --------------------------------------------------------

--
-- Table structure for table `staff_details`
--

CREATE TABLE `staff_details` (
  `user_id` varchar(10) NOT NULL,
  `accessible_pages` text DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `staff_details`
--

INSERT INTO `staff_details` (`user_id`, `accessible_pages`) VALUES
('S-001', 'page1,page2,pageA,pageB'),
('S-002', 'page1,pageA');

-- --------------------------------------------------------

--
-- Table structure for table `users`
--

CREATE TABLE `users` (
  `user_id` varchar(10) NOT NULL,
  `first_name` varchar(50) NOT NULL,
  `last_name` varchar(50) NOT NULL,
  `role` enum('customer','staff','doctor') NOT NULL DEFAULT 'customer',
  `email` varchar(100) NOT NULL,
  `phone` varchar(15) NOT NULL,
  `password` varchar(255) NOT NULL,
  `created_at` timestamp NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `users`
--

INSERT INTO `users` (`user_id`, `first_name`, `last_name`, `role`, `email`, `phone`, `password`, `created_at`) VALUES
('', 'cc', 'dd', 'customer', 'cc@g.com', '0712223344', '$2y$10$R4kFtIXBRZVnG8WJdSBosegFosew0ukxmfnckLnzV3IXz53NmMNHG', '2025-03-31 06:31:51'),
('C-001', '3', '3', 'customer', '3@g.com', '3', '$2y$10$G1Ams7PtBmAJUzTfwlQ.Q.pkc1CJmT17BeZ9tCI.Dm0McRfm2s/0e', '2025-03-12 03:52:41'),
('C-002', 'm', 'mm', 'customer', 'm@g.com', '0772222222', '$2y$10$ajmby2uLN9/eOkIK4hfLZuvwxb3HFNPSB0Zn4u/QeN4Nd8.7AojYu', '2025-03-12 04:19:41'),
('C-003', '4', '4', 'customer', '4@g.com', '222222', '$2y$10$t4Hf55gy4W6788NGlgSOnORZuoTXazkzWU7CVyI6TDPLNpcUiYlcm', '2025-03-21 06:53:24'),
('C-004', '7', '7', 'customer', '7@g.com', '77777', '$2y$10$ICwBGXIS0KT53KRC6tXwMOJSQHLqLZHy5fLaViSJN7qx8zB2rGhPK', '2025-03-26 09:31:10'),
('C-005', '8', '8', 'customer', '8@g.com', '8888', '$2y$10$4uFyytBpwroNRNLw0RngJu5Bqp.cXC2XztyUA2Me7j.U8QQbnT/Tu', '2025-03-26 09:35:02'),
('C-006', '9', '9', 'customer', '9@gmail.com', '0707586432', '$2y$10$/JyNPAgwVK/0Qpo0Cl9dt.rhmYZEsBpDuaqEbXno6nsLBFxnMPRaG', '2025-03-28 13:44:50'),
('C-007', 'Janithye', 'Priyabashana', 'customer', 'janithye123@gmail.com', '0771113454', '$2y$10$Q7xijpWWar3zuQCrHtmeNeK.qjg.fyGuW6CytIdUpNLjYABosiXeq', '2025-03-28 13:50:39'),
('C-008', 'san', 'sew', 'customer', 'san123@gmai.com', '0712345343', '$2y$10$aD2ydlQopeP9Ey0RS.OY1OLyRQqUFQCOiZ2Nt08t17jODlaInd3mm', '2025-03-28 13:56:21'),
('C-009', 'ss', 'mm', 'customer', 'ss@gmail.com', '0778965464', '$2y$10$UT8hkFUoyml03lCfy3g2..a4QKI81FJAE9nl36i0Oz9OZx3pY4bSC', '2025-03-31 04:54:42'),
('C-010', 'p', 'pp', 'customer', 'p@g.com', '0755556677', '$2y$10$0DmwiedApBE1D8oUQ3B4ven1zLtnKatUqdlsZoAxcYr3aQjBuUkwm', '2025-03-31 06:50:11'),
('C-011', 'v', 'vv', 'customer', 'v@g.com', '078555794', '$2y$10$FeXNuRUY4kV0/g0biTbxo.KqjxB0WUTfLsOKiGQaTQjOacq7/J1ku', '2025-03-31 06:53:47'),
('C-012', 'Sanduni', 'sewwandi', 'customer', 'sanduni2003822madu@gmail.com', '0778747345', '$2y$10$tX6Bs8fa757EAnPXPgBi0u0Us83cTVYTpYk5s4zWI8wFXPxUtBZou', '2025-04-02 05:16:57'),
('C-013', 'Sandali', 'Malnethmi', 'customer', 'sanmalhas19@gmail.com', '0779181199', '$2y$10$1AuEaZmrQTFQkiWgMI1Y0OIVttBwenYdy3eJvJmAwAaJP7OZtymji', '2025-04-02 08:45:44'),
('D-001', '2', '2', 'doctor', '2@g.com', '2', '$2y$10$U.rIhbjlQO1Zf/SXXE7unuFdrbuOkGK7anIBEM0YrqCtpodo0HywG', '2025-03-12 03:56:35'),
('D-002', 'Malaka', 'Dissanayake', 'doctor', 'malaka@g.com', '0112223454', '$2y$10$BfS2ledTk3yd7K0XjIKoK.wB/01Hj./eNYSZbzlm66sWsB/bZq1GO', '2025-04-01 09:01:42'),
('D-003', 'Sanjaya', 'Perera', 'doctor', 'sanjaya@gmail.com', '0778934222', '$2y$10$WuuH0yUjAHwzfcmg.wMTvezvAXFv7Xlz8xr/LfC2pEjqXieIPy3O.', '2025-04-01 14:05:48'),
('D-004', 'Nimalka', 'Abewikrama', 'doctor', 'Nimalka@gmail.com', '0783336757', '$2y$10$9qyIxuNlEbTwvh.kjsH2yeh9t0vGYiYHXwlQ2nSZCj6XruvLjLLG6', '2025-04-01 14:13:03'),
('D-005', 'Darshana', 'Hapukotuwa', 'doctor', 'darshana@gmail.com', '0717298822', '$2y$10$iu/nnbZ.JOAFY8OkphGgk.DZAddu1L8XY15rNfzz4nMc.YUqFsUNK', '2025-04-01 14:18:38'),
('S-001', '1', '1', 'staff', '1@g.com', '1', '$2y$10$Gqlh2YSIiygDdjE5XOwZOukACHfcgVppj5fR9vdyhgdVs7oIqBL0q', '2025-03-12 03:57:58'),
('S-002', 'sandu', 'madu', 'staff', 'san@g.com', '0771111111', '$2y$10$U5Y1L4XJhjXcsR6Zqlxi4ujNGgTdnN8EFokXHceJ7d81eSh4mpnFG', '2025-03-12 04:02:14');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `customer_details`
--
ALTER TABLE `customer_details`
  ADD PRIMARY KEY (`user_id`);

--
-- Indexes for table `doctor_details`
--
ALTER TABLE `doctor_details`
  ADD PRIMARY KEY (`user_id`);

--
-- Indexes for table `staff_details`
--
ALTER TABLE `staff_details`
  ADD PRIMARY KEY (`user_id`);

--
-- Indexes for table `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`user_id`),
  ADD UNIQUE KEY `email` (`email`),
  ADD UNIQUE KEY `phone` (`phone`);

--
-- Constraints for dumped tables
--

--
-- Constraints for table `customer_details`
--
ALTER TABLE `customer_details`
  ADD CONSTRAINT `customer_details_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`) ON DELETE CASCADE;

--
-- Constraints for table `doctor_details`
--
ALTER TABLE `doctor_details`
  ADD CONSTRAINT `doctor_details_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`) ON DELETE CASCADE;

--
-- Constraints for table `staff_details`
--
ALTER TABLE `staff_details`
  ADD CONSTRAINT `staff_details_ibfk_1` FOREIGN KEY (`user_id`) RE
