import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Header from "./components/Header";
import Home from "./components/Home";
import Coins from "./components/Coins";
import Exchanges from "./components/Exchanges";
import CoinDetails from "./components/CoinDetails";
import Footer from "./components/Footer";


function App() {
  return (
    <Router>
      <Header />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/coins" element={<Coins />} />
        <Route path="/exchanges" element={<Exchanges />} />
        <Route path="/coin/:id" element={<CoinDetails />} />
      </Routes>
     <Footer/>
      
    </Router>
  );
}

export default App;

import { Box, Image, Text } from "@chakra-ui/react";
import React from "react";
import btcSrc from "../assets/btc.png";
import { motion } from "framer-motion";

const Home = () => {
  return (
    <Box bgColor={"Black"} w={"full"} h={"85vh"}>
      <motion.div
        style={{
          height: "80vh",
        }}
        animate={{
          translateY: "20px",
        }}
        transition={{
          duration: 2,
          repeat: Infinity,
          repeatType: "reverse",
        }}
      >
        <Image
          w={"full"}
          h={"full"}
          objectFit={"contain"}
          src={btcSrc}
          filter={"grayscale(1)"}
        />
      </motion.div>

      <Text
        fontSize={"6xl"}
        textAlign={"center"}
        fontWeight={"thin"}
        
        mt={"-20"}
      >
        Welcome To Royal
      </Text>
    </Box>
  );
};

export default Home;

import { Button, HStack } from "@chakra-ui/react";
import { px } from "framer-motion";
import React from "react";
import { Link } from "react-router-dom";

const Header = () => {
  return (
    <HStack p={"4"} shadow={"base"} bgColor={"White"}>
      <nav color="Blackl"> Restaurent landing Page</nav>
      <Button variant={"unstyled"} color={"Black"} paddingLeft={900}>
        <Link to="/">Home</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">Gallery</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">Shop</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">Blog</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">About</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">Team</Link>
      </Button>
      <Button variant={"unstyled"} color={"Black"}>
        <Link to="/">Contact</Link>
      </Button>
      
    </HStack>
  );
};

export default Header;
import { Avatar, Box, Stack, Text, VStack } from "@chakra-ui/react";
import React from "react";

const avatarSrc = "https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1";
const Footer = () => {
  return (
    <Box
      bgColor={"blackAlpha.900"}
      color={"whiteAlpha.700"}
      minH={"48"}
      px={"16"}
      py={["16", "8"]}
    >
      <Stack direction={["column", "row"]} h={"full"} alignItems={"center"}>
        <VStack w={"full"} alignItems={["center", "flex-start"]}>
          <Text fontWeight={"bold"}>About Us</Text>
          <Text
            fontSize={"sm"}
            letterSpacing={"widest"}
            textAlign={["center", "left"]}
          >
            We are the best Restaurent  in India, we provide best 
            Service to visitors
          </Text>
        </VStack>

        <VStack>
          <Avatar boxSize={"28"} mt={["4", "0"]} src={avatarSrc} />
          <Text>Founder Mr.Aashish Jadhav</Text>
        </VStack>
      </Stack>
    </Box>
  );
};

export default Footer;
